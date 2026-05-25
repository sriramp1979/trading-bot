---
description: Pre-market research workflow — run before market open. Researches catalysts and writes today's trade ideas to RESEARCH-LOG.md.
---

You are running the pre-market research workflow.
DATE=$(date +%Y-%m-%d)

Note: credentials come from local .env file (auto-loaded by alpaca.sh).
No commit/push needed — local runs write files directly.

STEP 1 — Read memory for context:
- memory/TRADING-STRATEGY.md (full file)
- memory/SECTOR-LOG.md (full file)
- tail -n 30 memory/TRADE-LOG.md
- grep -A 50 "## $DATE" memory/RESEARCH-LOG.md (today's entry only; skip if not found)

STEP 2 — Pull live account state:
  bash scripts/alpaca.sh account
  bash scripts/alpaca.sh positions
  bash scripts/alpaca.sh orders

STEP 3 — Research market context (4 web searches max — paper trading mode).
Use native WebSearch tool for each query:
1. "S&P 500 futures premarket [DATE]"
2. "VIX level today [DATE]"
3. "Top stock market catalysts today [DATE]"
4. News on each currently-held ticker (one search per ticker; skip if no open positions)

STEP 4 — Write a dated entry to memory/RESEARCH-LOG.md:
- Account snapshot (equity, cash, buying power, daytrade count)
- Market context (S&P futures, VIX, today's catalysts)
- 2-3 actionable trade ideas WITH catalyst + entry/stop/target and sector classification
- Risk factors for the day
- Decision: TRADE or HOLD (default HOLD — patience > activity)

STEP 5 — Auto-trim RESEARCH-LOG.md to keep only the last 5 entries:
Keep only entries from the last 5 trading days.
Append a "--- TRIMMED [DATE] ---" marker before the oldest kept entry.

STEP 6 — Notification: silent (ClickUp disabled). Print a one-line summary to console only.
