# Research Log

Daily pre-market research entries will be appended here.
Format each entry:

## YYYY-MM-DD — Pre-market Research

### Account
- Equity: $X
- Cash: $X
- Buying power: $X
- Daytrade count: N

### Market Context
- S&P 500 futures:
- VIX:
- Today's catalysts:
- Earnings before open:

### Trade Ideas
1. TICKER — catalyst, entry $X, stop $X, target $X, R:R X:1
2. ...

### Risk Factors
- ...

### Decision
TRADE or HOLD (default HOLD if no edge)

## 2026-10-23 — Pre-market Research

### Account
- Equity: $97,434.22
- Cash: $84,954.22 (87.2%)
- Buying power: $374,760.88
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 19) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $32.00 | +$456.30 (+3.80%) | $30.4065 (trailing 10%, HWM $33.785) | 5.0% |

CVE GTC trailing stop confirmed live. Deployed 12.8% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found (stale results only) — check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: none verified; next week busy (Fed meeting, Trump–Xi, mega-cap earnings)
- Earnings before open: none held (CVE ~Oct 29-30)

### Position News
- **CVE** ($32.00, +3.80%): no new news found; fell -3.4% Oct 22 (oil). Q3 ~Oct 29-30. Stop 5.0% away, -7% cut line ~$28.67. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Sector OK. Limit <= +0.5% of ask, stop 8%, target +16%. Skip if spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%.
3. JPM add — Financials — limit order, spread check first.
(Unverified today — no fresh catalyst search results; carried from Oct 22.)

### Risk Factors
- Cash 87.2%: Rule 12 gate applies at open unless VIX >22 or futures gap < -2%
- IEX-only quotes gave wide spreads Oct 20 — limit orders near last trade, retry at midday
- CVE oil-driven weakness; stop 5% away
- Search data stale: no live futures/VIX
- ClickUp env vars missing — no alert channel; no urgent items today

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

## 2026-10-22 — Pre-market Research

### Account
- Equity: $98,023.12
- Cash: $84,954.22 (86.7%)
- Buying power: $376,409.80
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 19) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $33.51 | +$1,045.20 (+8.69%) | $30.4065 (trailing 10%, HWM $33.785) | 9.3% |

CVE GTC trailing stop confirmed live. Deployed 13.3% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found (stale results only) — check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: no dated list found. Q3 earnings season ongoing; stocks trading off bonds/yields, oil/Iran headlines
- Earnings before open: none held (CVE Oct 29-30)

### Position News
- **CVE** ($33.51, +8.69%): no new news; Q3 earnings ~Oct 29-30, consensus EPS ~$1.07, analysts mostly Buy; Athabasca deal pending. Below +15% tighten trigger. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Sector OK (INTC loss = 1). Limit <= +0.5% of ask, stop 8%, target +16% (2:1). Skip if spread >1% or >+6% extended.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%.
3. JPM add — Financials — bank Q3 follow-through; limit order, spread check first.
(Unverified today — no fresh catalyst search results; carried from Oct 21.)

### Risk Factors
- Cash 86.7%: Rule 12 gate applies at open unless VIX >22 or futures gap < -2%
- IEX-only quotes gave 3-7% spreads Oct 20 — limit orders near last trade, retry at midday
- Yields/oil: valuation pullback risk
- Search data stale: no live futures/VIX
- ClickUp env vars missing — no alert channel

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

## 2026-10-21 — Pre-market Research

### Account
- Equity: $97,991.92
- Cash: $84,954.22 (86.7%)
- Buying power: $376,322.44
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 19) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $33.43 | +$1,014.00 (+8.43%) | $30.4065 (trailing 10%, HWM $33.785) | 9.0% |

CVE GTC trailing stop confirmed live. Deployed 13.3% — far below 60% Rule-12 floor. Oct 20 add blocked by wide IEX spreads.

### Market Context
- S&P 500 futures: no same-day data found (stale results only). Last known S&P ~7,811 (Oct 9). Check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: no dated list found. Q3 earnings season ongoing (mega-cap tech reports late Oct); 10Y ~5.25%, oil/Iran headlines
- Earnings before open: none held (CVE Oct 29-30)

### Position News
- **CVE** ($33.43, +8.43%): no new news found; Athabasca deal pending (close Dec). Below +15% tighten trigger. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Sector OK (INTC loss = 1). Limit <= +0.5% of ask, stop 8%, target +16% (2:1). Skip if spread >1% or >+6% extended.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%.
3. JPM add — Financials — bank Q3 follow-through; use limit, spread check first.

### Risk Factors
- Cash 86.7%: Rule 12 gate applies at open unless VIX >22 or futures gap < -2%
- IEX-only quotes gave 3-7% spreads Oct 20 — use limit orders near last trade, retry at midday
- 10Y ~5.25% + oil: valuation pullback risk
- Search data stale again: no live futures/VIX
- ClickUp env vars missing — no alert channel

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

## 2026-10-20 — Pre-market Research

### Account
- Equity: $98,093.32
- Cash: $84,954.22 (86.6%)
- Buying power: $376,606.36
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 19) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $33.69 | +$1,115.40 (+9.28%) | $30.249 (trailing 10%, HWM $33.61) | 10.2% |

CVE GTC trailing stop confirmed live. META stopped out Oct 19 (-8.1%). Deployed 13.4% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found via search (stale results only). Last known S&P ~7,811 (Oct 9), near record; breadth poor. Check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: no dated list found. 10Y yield ~5.25%, oil/Iran-Hormuz overhang; Q3 earnings season ramping; Fed + Trump-Xi headlines next week
- Earnings before open: none held (CVE Oct 29)

### Position News
- **CVE** ($33.69, +9.28%): New high; Athabasca deal digestion, no new news. Below +15% tighten trigger. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Tech OK (reset Jul 24; INTC loss = 1). Limit <= +0.5% of ask, stop 8% below entry, target +16% (2:1). Skip if >+6% extended or spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%. Sector OK.
3. JPM add — Financials — big-bank Q3 follow-through; watch only.

### Risk Factors
- Cash 86.6%: Rule 12 gate forces >=1 add at open unless VIX >22 or futures gap < -2% — verify live
- 10Y ~5.25% + oil: valuation pullback risk; index near records, poor breadth
- Search data stale again: confirm futures/VIX via Alpaca quotes
- Communication Services (META) exit counts as failed trade (1); no new comm-services entry
- ClickUp env vars missing — no alert channel

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

--- TRIMMED 2026-10-23 ---

## 2026-10-19 — Pre-market Research

### Account
- Equity: $98,162.61
- Cash: $71,071.51 (72.4%)
- Buying power: $360,141.12
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 19) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $32.87 | +$795.60 (+6.62%) | $29.862 (trailing 10%, HWM $33.18) | 9.2% |
| META | 20 | $755.722 | $713.59 | -$842.64 (-5.58%) | $694.143 (trailing 10%, HWM $771.27) | 2.7% |

Both GTC trailing stops confirmed live. Deployed 27.6% — far below 60% Rule-12 floor. META −5.6% vs −7% cut line ($702.78, 1.5% away).

### Market Context
- S&P 500 futures: no same-day data found via search (stale results only). Check live at open
- VIX: no same-day reading found; last known ~16 (Jul 31) / ~15.3 (Oct 2) — assume <22 gate, verify live
- Today's catalysts: no dated catalyst list found. Big-bank/Q3 earnings season ongoing; macro calendar unverified
- Earnings before open: none held (META ~Oct 28 AMC est., CVE ~Oct 29)

### Position News
- **CVE** ($32.87, +6.62%): No new news found. Athabasca deal digestion. Cushion 9.2%. HOLD
- **META** ($713.59, -5.58%): No new catalyst; AI-capex worries ahead of ~Oct 28 Q3 print (Q2 EPS missed on costs). Stop $694.14 is 2.7% below. Cut at ≤$702.78 (−7%) per rule. HOLD unless breached

### Trade Ideas
1. QCOM — Technology — AI/semis carry-over from prior ideas (unfilled). Tech OK (INTC loss = 1). Limit ≤ +0.5% of ask, stop 8% below entry, target +16% (2:1). Skip if >+6% extended or spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Live spread <1% required; stop 8%, target +16%, R:R 2:1. Sector OK.
3. JPM-adjacent financials add — Financials — watch big-bank earnings reaction; not actionable pre-open.

### Risk Factors
- Cash 72.4%: Rule 12 gate (deployed <60%) forces ≥1 add at open unless VIX >22 or futures gap < -2% — verify live
- META near −7% cut line; weak into earnings
- Search data stale again: futures/VIX unverified, confirm via Alpaca quotes
- ClickUp env vars missing — no alert channel; no urgent items today

### Decision
TRADE (Rule 12 forced add, 1 position max, ≤15% sizing, limit order after live spread check). Prefer QCOM or MRNA; HOLD instead if futures gap < -2% or VIX >22. Real 10% trailing GTC stop immediately after fill.
