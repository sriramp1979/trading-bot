---
description: Weekly review workflow — run Friday at 4:15 PM ET. Computes week stats and writes review to WEEKLY-REVIEW.md.
---

You are running the Friday weekly review workflow.
DATE=$(date +%Y-%m-%d)

Note: credentials come from local .env file (auto-loaded by alpaca.sh).
No commit/push needed — local runs write files directly.

STEP 1 — Read memory for full week context:
- memory/WEEKLY-REVIEW.md (match existing template exactly for new entry)
- memory/TRADING-STRATEGY.md (full file)
- memory/SECTOR-LOG.md (full file — call out any Status = EXIT sectors)
- ALL this week's entries in memory/TRADE-LOG.md
- ALL this week's entries in memory/RESEARCH-LOG.md

STEP 2 — Pull week-end state:
  bash scripts/alpaca.sh account
  bash scripts/alpaca.sh positions

STEP 3 — Compute the week's metrics:
- Starting portfolio (Monday AM equity from earliest EOD snapshot this week)
- Ending portfolio (today's equity from account call)
- Week return ($ and %)
- S&P 500 week return:
  Use native WebSearch tool: "S&P 500 weekly performance week ending [DATE]"
- Trades taken (W/L/open)
- Win rate (closed trades only)
- Best trade, worst trade
- Profit factor (sum winners / |sum losers|)
- Sector EXIT events this week (from SECTOR-LOG.md)

STEP 4 — Append full review section to memory/WEEKLY-REVIEW.md:
- Week stats table
- Closed trades table
- Open positions at week end
- What worked (3-5 bullets)
- What didn't work (3-5 bullets)
- Key lessons learned
- Adjustments for next week
- Overall letter grade (A-F)

STEP 5 — If a rule needs to change (proven out for 2+ weeks or failed badly):
  Update memory/TRADING-STRATEGY.md and call out the change in the review.
  Reset SECTOR-LOG.md Status = EXIT sectors if 2+ weeks have passed without new trades.

STEP 6 — Notification: ClickUp disabled. Print week summary to console (≤15 lines).
