---
description: Market-open execution workflow — run ~9:35 AM ET after the bell. Executes planned trades from research log.
---

You are running the market-open execution workflow.
DATE=$(date +%Y-%m-%d)

Note: credentials come from local .env file (auto-loaded by alpaca.sh).
No commit/push needed — local runs write files directly.

STEP 0 — Check for PDT-blocked stops from previous days:
  grep "PDT-blocked, set tomorrow AM" memory/TRADE-LOG.md
  For each found entry, extract SYMBOL and QTY.
  Check if position still exists: bash scripts/alpaca.sh position SYM
  If position exists and has no open GTC stop order, place the stop now:
    bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"sell","type":"trailing_stop","trail_percent":"10","time_in_force":"gtc"}'
  Update the TRADE-LOG entry: replace "PDT-blocked, set tomorrow AM" with "Stop placed [DATE] [ORDER_ID]"
  Update "## Week of... | Trades: N/3" header if applicable.

STEP 0B — Market hours check:
  CLOCK=$(bash scripts/alpaca.sh clock)
  If is_open == false:
    Print "Market closed — skipped" to console and exit.

STEP 1 — Read memory for today's plan:
- memory/TRADING-STRATEGY.md (full file)
- memory/SECTOR-LOG.md (full file)
- grep -A 50 "## $DATE" memory/RESEARCH-LOG.md (today's entry only)
  If missing, run pre-market STEPS 1-3 inline before proceeding.
- tail -n 30 memory/TRADE-LOG.md (for weekly trade count from "## Week of..." header)

STEP 2 — Re-validate with live data:
  bash scripts/alpaca.sh account
  bash scripts/alpaca.sh positions
  bash scripts/alpaca.sh quote <each planned ticker>
  Verify bid/ask spread not wide or halted (skip if ap or bp is 0).

STEP 3 — Hard-check rules BEFORE every order. Skip any trade that fails; log the reason:
- Total positions after trade <= 6
- Trades this week (from "## Week of... | Trades: N/3" header) <= 3
- Position cost <= 20% of equity
- Position cost <= available cash
- Catalyst documented in today's RESEARCH-LOG
- daytrade_count leaves room (PDT: under 3 on sub-$25k account)
- Instrument is a stock
- Sector does NOT have Status = EXIT in SECTOR-LOG.md

STEP 4 — Execute approved buys (market orders, day TIF):
  bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"buy","type":"market","time_in_force":"day"}'
  Wait for fill confirmation before placing the stop.

STEP 5 — Immediately place 10% trailing stop GTC for each new position:
  bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"sell","type":"trailing_stop","trail_percent":"10","time_in_force":"gtc"}'
  If Alpaca rejects with PDT error, fall back to fixed stop 10% below entry:
    bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"sell","type":"stop","stop_price":"X.XX","time_in_force":"gtc"}'
  If also blocked, queue in TRADE-LOG as "PDT-blocked, set tomorrow AM".

STEP 6 — Append each trade to memory/TRADE-LOG.md (match existing format):
  Date, ticker, side, shares, entry price, stop level, thesis, target, R:R.
  Update "## Week of... | Trades: N/3" header, incrementing N for each buy.
  Update memory/SECTOR-LOG.md: add ticker to sector row.

STEP 7 — Notification: ClickUp disabled. Print trade summary to console only if trades placed.
