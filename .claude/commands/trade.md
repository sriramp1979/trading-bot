---
description: Manual trade helper with strategy-rule validation. Usage — /trade SYMBOL SHARES buy|sell
---

Execute a manual trade with full rule validation. Refuse if any rule fails.

Args: SYMBOL SHARES SIDE (buy or sell). If missing, ask.

1. Pull state: account, positions, quote SYMBOL (capture ask price P).
   bash scripts/alpaca.sh account
   bash scripts/alpaca.sh positions
   bash scripts/alpaca.sh quote SYMBOL

2. Read memory for context:
   - memory/TRADING-STRATEGY.md
   - memory/SECTOR-LOG.md
   - tail -n 30 memory/TRADE-LOG.md (weekly trade count from "## Week of..." header)

3. For BUY, validate ALL of these — if any fail, STOP and print the failed checks:
   - Total positions after fill <= 6
   - Trades this week (from "## Week of... | Trades: N/3" header) + 1 <= 3
   - SHARES * P <= 20% of equity
   - SHARES * P <= available cash
   - daytrade_count < 3
   - Catalyst documented (ask for thesis if not in today's RESEARCH-LOG)
   - Instrument is a stock (not an option)
   - Sector does NOT have Status = EXIT in memory/SECTOR-LOG.md

4. For SELL, confirm position exists with right qty. No other checks.

5. Print order JSON + validation results, ask "execute? (y/n)".

6. On confirm:
   bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"buy|sell","type":"market","time_in_force":"day"}'

7. For BUYs, immediately place 10% trailing stop GTC:
   bash scripts/alpaca.sh order '{"symbol":"SYM","qty":"N","side":"sell","type":"trailing_stop","trail_percent":"10","time_in_force":"gtc"}'
   If Alpaca rejects with PDT error, fall back to fixed stop 10% below entry.
   If also blocked, queue in TRADE-LOG as "PDT-blocked, set tomorrow AM".

8. Log to memory/TRADE-LOG.md matching existing format:
   - Date, ticker, side, shares, entry price, stop level, thesis, target, R:R
   - Update "## Week of... | Trades: N/3" header, incrementing N
   - Update memory/SECTOR-LOG.md for the traded sector

9. Note: ClickUp notifications are disabled. No clickup.sh call needed.
