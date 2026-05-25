---
description: Midday scan workflow — run at noon ET. Cuts losers, tightens stops on winners, checks theses.
---

You are running the midday scan workflow.
DATE=$(date +%Y-%m-%d)

Note: credentials come from local .env file (auto-loaded by alpaca.sh).
No commit/push needed — local runs write files directly.

STEP 0B — Market hours check:
  CLOCK=$(bash scripts/alpaca.sh clock)
  If is_open == false:
    Print "Market closed — skipped" to console and exit.

STEP 1A — Early exit check (pull positions before reading memory):
  POSITIONS=$(bash scripts/alpaca.sh positions)
  If no positions exist: print "No open positions — nothing to do" and exit.
  If all positions have unrealized_plpc between -0.05 and +0.12: print "All positions within band — no action needed" and exit.
  Only proceed to full workflow if any position is outside the -5% / +12% band.

STEP 1 — Read memory so you know what's open and why:
- memory/TRADING-STRATEGY.md (exit rules, full file)
- memory/SECTOR-LOG.md (full file)
- tail -n 30 memory/TRADE-LOG.md (entries, original thesis per position, stops)
- grep -A 50 "## $DATE" memory/RESEARCH-LOG.md (today's entry only)

STEP 2 — Pull current state:
  bash scripts/alpaca.sh positions
  bash scripts/alpaca.sh orders

STEP 3 — Cut losers immediately. For every position where unrealized_plpc <= -0.07:
  1. bash scripts/alpaca.sh close SYM
  2. Find the associated stop order fresh by symbol — do NOT use a memorized order ID:
       bash scripts/alpaca.sh orders open
       Filter where symbol == SYM AND side == sell AND type IN (trailing_stop, stop)
       Cancel each matching order: bash scripts/alpaca.sh cancel ORDER_ID
  3. Log exit to memory/TRADE-LOG.md: exit price, realized P&L, "cut at -7% per rule"
  4. Update memory/SECTOR-LOG.md: increment Consecutive Losses for the sector; if 2 consecutive, set Status = EXIT

STEP 4 — Tighten trailing stops on winners. For each eligible position:
  Cancel old trailing stop (look up by symbol — never use a memorized ID)
  Place new one:
    Up >= +20%: trail_percent "5"
    Up >= +15%: trail_percent "7"
  Never tighten within 3% of current price. Never move a stop down.

STEP 5 — Thesis check. If a thesis broke intraday, cut the position even if not at -7%:
  Document reasoning in memory/TRADE-LOG.md.
  Update memory/SECTOR-LOG.md accordingly.

STEP 6 — Optional intraday research. If something is moving sharply with no obvious cause:
  Use native WebSearch tool: "SYM stock news today [DATE]"
  Append an afternoon addendum to memory/RESEARCH-LOG.md if findings are material.

STEP 7 — Notification: ClickUp disabled. Print action summary to console only if action was taken.
