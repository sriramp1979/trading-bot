# Sector Log

## Active Sector Tracking
| Sector | Tickers Held | Consecutive Losses | Status |
|--------|-------------|-------------------|--------|
| Technology | — | 2 | EXIT |
| Healthcare | LLY, NVO | 0 | OK |
| Communication Services | — | 2 | EXIT |
| Consumer Discretionary | AMZN | 0 | OK |
| Financials | JPM | 0 | OK |

## Sector Exit History
| Sector | Exit Date | Reason |
|--------|-----------|--------|
| Communication Services | 2026-06-22 | 2 consecutive losses (META stop-out Jun 11, GOOGL thesis-break exit Jun 22 — dilution + FCF collapse + AI talent flight) |
| Technology | 2026-06-25 | 2 consecutive losses (NVDA stop-out Jun 5, NVDA stop-out Jun 25 — Micron sell-the-news selloff dragged GPU names; chip sector multiple compression) |

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
