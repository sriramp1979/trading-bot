# Sector Log

## Active Sector Tracking
| Sector | Tickers Held | Consecutive Losses | Status |
|--------|-------------|-------------------|--------|
| Technology | INTC | 1 | OK |
| Healthcare | — | 1 | OK |
| Communication Services | META | 0 | OK |
| Consumer Discretionary | — | 1 | OK |
| Financials | JPM | 0 | OK |
| Consumer Staples | — | 1 | OK |
| Energy | — | 0 | OK |
| Real Estate | — | 1 | OK |

## Sector Exit History
| Sector | Exit Date | Reason |
|--------|-----------|--------|
| Communication Services | 2026-06-22 | 2 consecutive losses (META stop-out Jun 11, GOOGL thesis-break exit Jun 22 — dilution + FCF collapse + AI talent flight) |
| Technology | 2026-06-25 | 2 consecutive losses (NVDA stop-out Jun 5, NVDA stop-out Jun 25 — Micron sell-the-news selloff dragged GPU names; chip sector multiple compression) |

## Sector Reset Log
| Sector | Reset Date | Reason |
|--------|-----------|--------|
| Communication Services | 2026-07-24 | EXIT status >4 weeks (since 2026-06-22) with no new trades in sector; Consecutive Losses reset to 0 per weekly-review rule |
| Technology | 2026-07-24 | EXIT status >4 weeks (since 2026-06-25) with no new trades in sector; Consecutive Losses reset to 0 per weekly-review rule |

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

## Data Note (2026-09-25 weekly review)
Healthcare, Consumer Discretionary, and Consumer Staples all show "1" Consecutive Losses
with no tickers held and no matching closed trade in TRADE-LOG.md — unverified seed values,
not evidence of a real loss. Real Estate's XLRE cut (2026-09-24, -7.57%) was Real Estate's
only trade ever, so its pre-existing "1" was treated the same way: this week's loss is
logged as the sector's 1st verified loss (Status stays OK), not a 2nd. Needs a one-time
manual audit/reset with the user rather than further automated changes.
