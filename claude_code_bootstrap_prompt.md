# Trading Bot — Claude Code Bootstrap Prompt

Paste this entire prompt into your Claude Code session opened in an empty directory.

---

You are setting up an autonomous paper trading bot. You have two reference documents:

1. **trading_bot_setup_guide.md** (Opus 4.7 Trading Bot Setup Guide) — the base blueprint
2. **trading_bot_addendum.md** — corrections and additions that override the base blueprint where they conflict

**Your task: implement this project from scratch following Part 10 of the base blueprint (Replication Checklist), with all addendum modifications applied.**

---

## Ground rules before you start

- Do NOT ask for any API credentials upfront. Build the full structure first. When you reach the local smoke test step, ask for credentials one at a time.
- Do NOT create a `.env` file until explicitly asked to during the smoke test step.
- Do NOT install the Claude GitHub App or create cloud routines — those require web UI steps the user will do manually. You will generate the routine prompt text files only.
- After completing the full setup, print a final checklist of manual steps the user must complete in the web UI.

---

## Execution order

### Phase 1 — Repository structure
1. Create the full directory structure from PDF Part 3.
2. Create all files listed below. For each file, apply addendum overrides before writing.

**Scripts (scripts/):**
- `alpaca.sh` — from PDF Appendix C, plus Addendum Fix S1 (clock subcommand) and Fix S2 (trailing stop coercion). Use `python3` not `python` everywhere.
- Do NOT create `clickup.sh` — notifications are disabled for now.
- Do NOT create `perplexity.sh` — see Addendum Fix S3.
- After creating scripts: `chmod +x scripts/*.sh`

**Root files:**
- `CLAUDE.md` — from PDF Appendix A. Do not add to it.
- `env.template` — from Addendum A8 (paper trading endpoint, no Perplexity vars).
- `.gitignore` — must include `.env`, `*.env`, `DAILY-SUMMARY.md`.
- `README.md` — one paragraph: what this is, how to run local smoke test, link to Part 7 for routine setup.

**Memory files (memory/):**
- `TRADING-STRATEGY.md` — from PDF Appendix H.1.
- `TRADE-LOG.md` — from PDF Appendix H.2, modified: add week header `## Week of [TODAY'S DATE] | Trades: 0/3` above the Day 0 entry.
- `RESEARCH-LOG.md` — from PDF Appendix H.3.
- `WEEKLY-REVIEW.md` — from PDF Appendix H.4.
- `PROJECT-CONTEXT.md` — from PDF Appendix H.5.
- `SECTOR-LOG.md` — from Addendum A5.

**Pre-commit hook:**
- Create `.git/hooks/pre-commit` from Addendum A6. Run `chmod +x .git/hooks/pre-commit`.

### Phase 2 — Slash commands (.claude/commands/)
Create all seven slash commands. For the five workflow commands (pre-market, market-open, midday, daily-summary, weekly-review), use the PDF Appendix G as the base but apply these modifications:
- Remove all Perplexity references; replace with native WebSearch instructions.
- Apply the memory read limits from Addendum Rule T1 (tail commands, date filters).
- Apply the midday early exit from Addendum Rule T4.
- Apply Fix W1 (PDT queued stop check) to market-open.
- Apply Fix W3 (stop cancellation by symbol) to midday.
- Apply Fix W4 (week header update) to market-open and trade slash commands.
- Apply Fix W5 (P&L fallback) to daily-summary.
- Add SECTOR-LOG.md read to all workflow commands alongside TRADING-STRATEGY.md.

### Phase 3 — Routine prompts (routines/)
Create the five routine prompt files. Each must be a complete, standalone prompt — no placeholder text. Follow the PDF Appendix F as the base, then apply:
- Full env/persistence blocks in every file (no `[same block as pre-market]` shortcuts) — see Addendum A7 for the exact block text.
- Remove all PERPLEXITY_* vars from the env check loop.
- Replace all `bash scripts/perplexity.sh` calls with: `Use native WebSearch tool for this query: "[query]"` — keep the same query topics from the PDF.
- Apply Rule T1 memory read limits (tail/grep commands) to every routine.
- Apply Rule T3 (4 web searches max for pre-market) to pre-market routine.
- Apply Rule T4 midday early exit to midday routine.
- Apply Fix W1 (PDT stop check Step 0) to market-open routine.
- Apply Fix W2 (market hours gate Step 0B) to market-open and midday routines.
- Apply Fix W3 (stop cancellation by symbol) to midday routine.
- Apply Fix W4 (week header) to market-open routine.
- Apply Fix W5 (P&L fallback) to daily-summary routine.
- Apply Fix W6: in weekly-review, SECTOR-LOG.md must be read and any status=EXIT sectors must be called out.
- Use cron schedules and ET timezone from Addendum A1.

### Phase 4 — Verification
After creating all files:
1. Print the full directory tree.
2. Run `bash -n scripts/alpaca.sh` and `bash -n scripts/clickup.sh` to check for syntax errors.
3. Verify `.env` does NOT exist.
4. Verify `scripts/perplexity.sh` does NOT exist.
5. Verify `scripts/clickup.sh` does NOT exist..
6. Confirm `.gitignore` contains `.env`.
7. Confirm `.git/hooks/pre-commit` exists and is executable.

### Phase 5 — Smoke test (credentials required)
**Stop here and tell the user:**
> "Structure is complete. Ready for local smoke test. Please provide your Alpaca paper trading API key."

Wait for each credential before asking for the next. Collect:
1. ALPACA_API_KEY
2. ALPACA_SECRET_KEY


Write these to `.env` (local only — already gitignored). Then run:
```bash
bash scripts/alpaca.sh account
bash scripts/alpaca.sh positions
bash scripts/alpaca.sh clock
```
Print the raw output. If all three return valid JSON, smoke test passes.

### Phase 6 — Manual steps summary
Print a numbered list of everything the user must complete manually:
1. Create a private GitHub repo and push this directory to it.
2. Install the Claude GitHub App on that repo (link: https://github.com/apps/claude).
3. In Claude Code web (claude.ai/code/routines), create each of the 5 routines — for each, specify: repo, branch (main), cron schedule from Addendum A1, and paste the corresponding routines/*.md file content verbatim as the prompt.
4. In each routine's environment settings: add ALPACA_API_KEY, ALPACA_SECRET_KEY, ALPACA_ENDPOINT (paper URL), ALPACA_DATA_ENDPOINT, CLICKUP_API_KEY, CLICKUP_WORKSPACE_ID, CLICKUP_CHANNEL_ID. No Perplexity vars.
5. Enable "Allow unrestricted branch pushes" toggle on each routine.
6. Hit "Run now" on the pre-market routine first to verify it commits to the repo.
7. Seed TRADE-LOG.md with an EOD snapshot matching today's date before the first live run.
8. Monitor the first full week of runs by checking git log on the repo daily.

---

## Constraints (enforce throughout)
- Every routine prompt must be self-contained. No cross-references to other files.
- No `.env` file in the cloud. The scripts read from process environment vars.
- `trail_percent`, `qty`, `stop_price` in Alpaca order JSON are always strings.
- WEEKLY-REVIEW.md is never opened during Mon–Thu automated runs.
- RESEARCH-LOG.md is trimmed to 5 entries at the end of each pre-market run.
- Market-open and midday routines exit immediately if `alpaca clock` returns `is_open: false`.
- All stop cancellations look up order IDs fresh by symbol — never from memory.
- Weekly trade count comes from the `## Week of... | Trades: N/3` header in TRADE-LOG, not from counting log entries.
