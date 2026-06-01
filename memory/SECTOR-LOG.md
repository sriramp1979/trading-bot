# Sector Log

## Active Sector Tracking
| Sector | Tickers Held | Consecutive Losses | Status |
|--------|-------------|-------------------|--------|
| Technology | NVDA, HPE | 0 | OK |
| Healthcare | LLY | 0 | OK |

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

## Rules
- After any trade is closed at a loss: increment that sector's Consecutive Losses
- After a win: reset Consecutive Losses to 0
- At 2 consecutive losses: set Status = EXIT and add to exit history
- Buy-side gate must reject any new trade in a sector with Status = EXIT
