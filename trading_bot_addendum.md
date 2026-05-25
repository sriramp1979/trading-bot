# Trading Bot — Implementation Addendum
**Supplements the Opus 4.7 Trading Bot Setup Guide PDF.**
**Where this document conflicts with the PDF, this document takes precedence.**

---

## A1 — Platform Decision (replaces PDF Part 7 scheduling discussion)

**Use Claude Code Routines. Do NOT use Cowork scheduled tasks.**

Cowork scheduled tasks stop when the computer sleeps. Pre-market fires at 6 AM — before the machine is reliably on. Routines run on Anthropic's cloud infrastructure; the computer does not need to be on.

**Pro plan constraints:**
- 5 automated routine runs per day (hard cap)
- Mon–Thu: 4 runs used (pre-market, market-open, midday, daily-summary) — 1 slot spare
- Friday: 5 runs used (above 4 + weekly-review) — zero spare
- Runs draw from the same 5-hour token window as interactive sessions

**No Perplexity API.** Every research query in the PDF that calls `bash scripts/perplexity.sh` is replaced by Claude's native WebSearch tool. Remove `scripts/perplexity.sh` from the repo entirely. Remove all PERPLEXITY_* vars from `env.template` and routine env configs. In every prompt where the PDF says "If Perplexity exits 3, fall back to native WebSearch", that fallback IS the primary path — no fallback language needed.

**Cron timezone: use America/New_York (ET), not America/Chicago (CT).**
ET is the market's native timezone. This eliminates DST ambiguity.

Corrected cron schedules (America/New_York):
```
Pre-market:     0 6 * * 1-5    (6:00 AM ET weekdays)
Market-open:    35 9 * * 1-5   (9:35 AM ET — 5 min after open)
Midday:         0 12 * * 1-5   (noon ET weekdays)
Daily-summary:  5 16 * * 1-5   (4:05 PM ET — 5 min after close)
Weekly-review:  15 16 * * 5    (4:15 PM ET Fridays)
```

---

## A2 — Token Optimization Rules (new section — mandatory)

These rules exist because each routine run draws from a shared 5-hour token window on the Pro plan. A bloated run can consume 10–20% of the daily window.

**Rule T1 — Memory read limits. Enforced in every prompt.**
| File | What to read |
|---|---|
| TRADING-STRATEGY.md | Full file (it is small and static) |
| TRADE-LOG.md | Last 30 lines only: `tail -n 30 memory/TRADE-LOG.md` |
| RESEARCH-LOG.md | Today's entry only. Use `grep -A 50 "## $DATE" memory/RESEARCH-LOG.md` |
| WEEKLY-REVIEW.md | **Friday only.** Never open on Mon–Thu. |
| PROJECT-CONTEXT.md | Never open during automated runs. Read once during local setup only. |

**Rule T2 — CLAUDE.md stays minimal.**
Do not add to the CLAUDE.md starter from Appendix A. Every line is loaded on every session.

**Rule T3 — Pre-market research: 4 web searches maximum for paper trading.**
Replace the 7+ queries in the PDF with these 4:
1. `S&P 500 futures premarket [DATE]`
2. `VIX level today [DATE]`
3. `Top stock market catalysts today [DATE]`
4. News on each currently-held ticker (one search per ticker, skip if no open positions)

Expand back to full research scope only when transitioning to live trading.

**Rule T4 — Midday early exit.**
Add this as Step 1A in the midday routine, before reading any memory:
```bash
# Pull positions first, exit immediately if no action needed
POSITIONS=$(bash scripts/alpaca.sh positions)
# If no positions exist, commit nothing and exit
# If all positions are between -5% and +12% unrealized, exit
# Only proceed to full workflow if any position is outside that band
```
On quiet days this saves the full cost of reading memory files and doing thesis checks.

**Rule T5 — Write memory concisely.**
Agent must match the exact table format in Appendix H. No free-form paragraphs. The EOD notes paragraph in daily-summary is capped at 3 sentences.

**Rule T6 — RESEARCH-LOG.md auto-trim.**
At the end of each pre-market run, after the commit, trim the research log to keep only the last 5 entries:
```bash
# Keep only entries from the last 5 trading days
# Append a --- TRIMMED [DATE] --- marker before the oldest kept entry
```
This prevents the file growing to thousands of tokens over weeks.

---

## A3 — Script Fixes (overrides Appendix C)

### Fix S1 — Market hours check (add to alpaca.sh)
Add a new subcommand `clock` to `scripts/alpaca.sh`:
```bash
clock)
  curl -fsS -H "$H_KEY" -H "$H_SEC" "$API/clock"
  ;;
```
Usage: `bash scripts/alpaca.sh clock` returns `{"is_open": true/false, "next_open": "...", "next_close": "..."}`.

Call this at the start of the market-open and midday workflows. If `is_open` is false, log "Market closed — [reason]" to TRADE-LOG, send no ClickUp message, skip commit, exit.

### Fix S2 — Trailing stop type coercion (add to alpaca.sh order subcommand)
After parsing the JSON body, before POSTing, pipe through python3 to coerce string fields:
```bash
order)
  body="${1:?usage: order '<json>'}"
  # Coerce qty, trail_percent, stop_price to strings — Alpaca requires strings
  body="$(echo "$body" | python3 -c "
import json,sys
d=json.load(sys.stdin)
for k in ('qty','trail_percent','stop_price'):
    if k in d and not isinstance(d[k], str):
        d[k] = str(d[k])
print(json.dumps(d))
")"
  curl -fsS -H "$H_KEY" -H "$H_SEC" -H "Content-Type: application/json" \
    -X POST -d "$body" "$API/orders"
  ;;
```

### Fix S3 — Remove perplexity.sh entirely
Delete `scripts/perplexity.sh`. Remove it from the repo. Claude's native WebSearch is the research tool. No wrapper needed.

### Fix S4 — Use python3 not python
In any remaining script that calls `python -c`, replace with `python3 -c`. Minimal cloud containers may not have `python` in PATH.

---

## A4 — Workflow Fixes (overrides PDF Part 5 and Appendix F)

### Fix W1 — Market-open: Step 0 — Check queued stops first
Insert before Step 1 of the market-open workflow:
```
STEP 0 — Check for PDT-blocked stops from previous days:
  grep "PDT-blocked, set tomorrow AM" memory/TRADE-LOG.md
  For each found entry, extract SYMBOL and QTY.
  Check if position still exists: bash scripts/alpaca.sh position SYM
  If position exists and has no open GTC stop order, place the stop now:
    bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"sell",
      "type":"trailing_stop","trail_percent":"10","time_in_force":"gtc"}'
  Update the TRADE-LOG entry: replace "PDT-blocked, set tomorrow AM" with
    "Stop placed [DATE] [ORDER_ID]"
```

### Fix W2 — Market-open: Step 2 — Market hours gate
Insert after Step 0:
```
STEP 0B — Market hours check:
  CLOCK=$(bash scripts/alpaca.sh clock)
  If is_open == false:
    Append one line to TRADE-LOG: "## [DATE] market-open — Market closed, skipped"
    Exit without commit.
```

### Fix W3 — Midday: Stop cancellation must match by symbol
Replace the generic "cancel ORDER_ID" instruction in midday Step 3 with:
```
For each position to close (unrealized_plpc <= -0.07):
  1. bash scripts/alpaca.sh close SYM
  2. Find the associated stop: bash scripts/alpaca.sh orders open
     Filter orders where symbol == SYM AND side == sell
       AND type IN (trailing_stop, stop)
     Cancel each matching order: bash scripts/alpaca.sh cancel ORDER_ID
  3. Log exit to TRADE-LOG
```
Never cancel by a memorised order ID. Always look up the order ID fresh by symbol.

### Fix W4 — Weekly trade counter in TRADE-LOG
Every time a trade is appended to TRADE-LOG.md, also update the week header:
```markdown
## Week of YYYY-MM-DD | Trades: N/3
```
The market-open and /trade slash command both increment N. The buy-side gate reads this header to check the weekly count — do not count log entries manually.

Update the TRADE-LOG.md seed (Appendix H.2) to include:
```markdown
## Week of YYYY-MM-DD | Trades: 0/3
## Day 0 — EOD Snapshot (pre-launch baseline)
...
```

### Fix W5 — Daily-summary P&L fallback
In daily-summary Step 1, finding yesterday's equity:
```
Primary: grep most recent "Portfolio:" line from tail of TRADE-LOG.md
Fallback (if not found): use today's equity from Alpaca account as baseline
  Log: "WARNING: no yesterday equity found, Day P&L = N/A"
  Do NOT skip the EOD snapshot — write it with Day P&L marked as N/A
```
This prevents a full workflow failure if yesterday's commit was missed.

---

## A5 — Memory Model Addition (supplements PDF Part 6)

### New file: memory/SECTOR-LOG.md
Add this file to the repo. Seed it at launch. The agent reads and updates it during market-open (new position), midday (thesis exit), and weekly-review.

```markdown
# Sector Log

## Active Sector Tracking
| Sector | Tickers Held | Consecutive Losses | Status |
|--------|-------------|-------------------|--------|
| (none yet) | | 0 | OK |

## Sector Exit History
| Sector | Exit Date | Reason |
|--------|-----------|--------|

## Sector Classification
Use these exact sector names (no variations):
- Energy
- Technology
- Healthcare
- Financials
- Consumer Discretionary
- Consumer Staples
- Industrials
- Materials
- Utilities
- Real Estate
- Communication Services
```

Rule: after any trade is closed at a loss, increment that sector's Consecutive Losses. After a win, reset to 0. At 2 consecutive losses, mark Status = EXIT and add to exit history. The buy-side gate must check this file: reject any new trade in a sector with Status = EXIT.

Add SECTOR-LOG.md to all workflow read steps alongside TRADING-STRATEGY.md.
Update memory file table in Part 6:

| File | Purpose | Write Cadence |
|---|---|---|
| SECTOR-LOG.md | Sector consecutive loss tracking | On every closed trade |

---

## A6 — Security Addition (new)

### Pre-commit hook — credential leak prevention
After creating the repo, add this file as `.git/hooks/pre-commit` and run `chmod +x .git/hooks/pre-commit`:

```bash
#!/usr/bin/env bash
# Block commits containing API key patterns
PATTERNS="ALPACA_API_KEY=sk|ALPACA_SECRET_KEY=|your_alpaca|your_clickup|your_perplexity"
if git diff --cached --name-only | xargs grep -lE "$PATTERNS" 2>/dev/null; then
  echo "ERROR: Commit blocked — possible API key detected in staged files."
  echo "Check staged files with: git diff --cached"
  exit 1
fi
```

This fires before every `git commit` locally. It does not run in the cloud container (which never has a `.env`), so it does not affect routine execution.

---

## A7 — Appendix F Placeholder Fix

The PDF Appendix F.2 (market-open) and F.3 (midday) contain placeholder text:
- `[same env block as pre-market]`
- `[same persistence block as pre-market]`

These are NOT real prompt text. When creating those two routines, copy the full env block and persistence block verbatim from F.1 into F.2 and F.3. Every routine must contain the complete text — no references to other routines.

The env block to paste into F.2 and F.3:
```
IMPORTANT — ENVIRONMENT VARIABLES:
- Every API key is ALREADY exported as a process env var:
  ALPACA_API_KEY, ALPACA_SECRET_KEY, ALPACA_ENDPOINT, ALPACA_DATA_ENDPOINT,
  CLICKUP_API_KEY, CLICKUP_WORKSPACE_ID, CLICKUP_CHANNEL_ID.
- There is NO .env file in this repo and you MUST NOT create, write, or source one.
- If a wrapper prints "KEY not set in environment" -> STOP, send one ClickUp alert
  naming the missing var, and exit. Do NOT create a .env as a workaround.
- Verify env vars BEFORE any wrapper call:
  for v in ALPACA_API_KEY ALPACA_SECRET_KEY \
            CLICKUP_API_KEY CLICKUP_WORKSPACE_ID CLICKUP_CHANNEL_ID; do
    [[ -n "${!v:-}" ]] && echo "$v: set" || echo "$v: MISSING"
  done

IMPORTANT — PERSISTENCE:
- Fresh clone. File changes VANISH unless committed and pushed.
  MUST commit and push at the final STEP.
```

Note: PERPLEXITY_* vars are removed from this block per Fix S3.

---

## A8 — Revised env.template (replaces Appendix B)

```bash
# Alpaca (paper trading to start — change endpoint for live)
ALPACA_ENDPOINT=https://paper-api.alpaca.markets/v2
ALPACA_DATA_ENDPOINT=https://data.alpaca.markets/v2
ALPACA_API_KEY=your_alpaca_paper_api_key_here
ALPACA_SECRET_KEY=your_alpaca_paper_secret_key_here


```

Changes from PDF:
- Default endpoint is paper trading URL, not live. Change explicitly when going live.
- Perplexity vars removed entirely.

---

## A9 — Replication Checklist Additions (supplements PDF Part 10)

Insert these steps into the PDF Part 10 checklist, in order:

After "Copy the three wrapper scripts from Appendices C–E":
- ☐ Apply Fix S1 (add `clock` subcommand to alpaca.sh)
- ☐ Apply Fix S2 (add trailing stop coercion to alpaca.sh order subcommand)
- ☐ Delete scripts/perplexity.sh — do not create it
- ☐ Replace all `python` calls with `python3` in any script

After "Seed the five memory files from Appendix H":
- ☐ Seed memory/SECTOR-LOG.md from A5 above
- ☐ Add week header `## Week of YYYY-MM-DD | Trades: 0/3` to TRADE-LOG.md above the Day 0 entry

After "Add .env to .gitignore":
- ☐ Create `.git/hooks/pre-commit` from A6 above and `chmod +x` it

After "Sign up for Alpaca (paper to start), Perplexity, ClickUp":
- ☐ Remove Perplexity from this list. Not needed.

Replace "The five cron schedules" with the schedules from A1 above (ET timezone).

When creating routines:
- ☐ Confirm F.2 and F.3 have full env/persistence blocks, not placeholders
- ☐ Confirm all routine env configs contain NO Perplexity vars
- ☐ Confirm ALPACA_ENDPOINT is set to paper trading URL until you deliberately go live
