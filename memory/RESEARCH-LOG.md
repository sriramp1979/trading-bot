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

## 2026-10-29 — Pre-market Research

### Account
- Equity: $97,679.80
- Cash: $84,954.22 (87.0%)
- Buying power: $375,448.51
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 26) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $32.63 | +$701.88 (+5.84%) | $30.4065 (trailing 10%, HWM $33.785) | 6.8% |

CVE GTC trailing stop confirmed live. Deployed 13.0% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found (stale results only) — check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: big-cap earnings (MSFT, GOOGL, META, LLY, CAT per listing); hot Sept CPI (+0.6% m/m, 3.7% y/y), yields elevated, oil ~$98-104 / Iran headlines
- Earnings before open: none held (CVE Q3 ~Oct 29-30)

### Position News
- **CVE** ($32.63, +5.84%): no new news found; Q3 earnings ~Oct 29-30. Below +15% tighten trigger. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Sector OK. Limit <= +0.5% of ask, stop 8%, target +16% (2:1). Skip if spread >1% or >+6% extended.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%.
3. JPM add — Financials — limit order, spread check first.
(Unverified today — no fresh catalyst data; carried forward. Both QCOM/MRNA skipped Oct 28 on 5%+ spreads.)

### Risk Factors
- Cash 87.0%: Rule 12 gate applies at open unless VIX >22 or futures gap < -2%
- Wide IEX spreads — limit orders near last trade, retry at midday
- Mega-cap earnings tonight/today + hot CPI/yields: volatility risk
- Search data stale: no live futures/VIX
- ClickUp env vars missing — no alert channel

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

## 2026-10-28 — Pre-market Research

### Account
- Equity: $97,449.82
- Cash: $84,954.22 (87.2%)
- Buying power: $374,804.56
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 26) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $32.04 | +$471.90 (+3.93%) | $30.4065 (trailing 10%, HWM $33.785) | 5.1% |

CVE GTC trailing stop confirmed live. Deployed 12.8% — far below 60% Rule-12 floor. No trades executed Oct 27 despite plan.

### Market Context
- S&P 500 futures: no same-day data found (stale results only) — check live at open
- VIX: no same-day reading found; assume <22 gate — verify live
- Today's catalysts: none verified; week = Fed meeting, Trump–Xi, Honeywell spinoff, Amazon/mega-cap earnings
- Earnings before open: none held (CVE Oct 29-30, ±9.6% implied)

### Position News
- **CVE** ($32.04, +3.93%): No new news found. Earnings Oct 29-30 — binary risk, gap through 10% trail possible. Below +15% tighten trigger. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Tech OK (1 loss). Limit <= +0.5% of ask, stop 8% below entry, target +16% (2:1). Skip if >+6% extended or spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1%; stop 8%, target +16%. Sector OK.
3. JPM — Financials — big-bank follow-through; watch only.

### Risk Factors
- Cash 87.2%: Rule 12 gate forces >=1 add at open unless VIX >22 or futures gap < -2% — verify live
- CVE earnings Oct 29-30 gap risk; CVE only 5.1% above stop
- Rates/oil, poor breadth; Fed meeting this week
- Search data stale again: confirm futures/VIX via Alpaca quotes
- ClickUp env vars missing — no alert channel

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

## 2026-10-27 — Pre-market Research

### Account
- Equity: $98,019.22
- Cash: $84,954.22 (86.7%)
- Buying power: $376,398.88
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 26) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $33.50 | +$1,041.30 (+8.66%) | $30.4065 (trailing 10%, HWM $33.785) | 9.2% |

CVE GTC trailing stop confirmed live. Deployed 13.3% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found via search (stale results only). Check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: no dated list found. Busy earnings week; Fed meeting + Trump-Xi headlines this week
- Earnings before open: none held (CVE Oct 29-30, implied move ~±9.6%)

### Position News
- **CVE** ($33.50, +8.66%): No new company news. Q3 earnings Oct 29-30 (±9.6% implied) — binary risk inside 10% trail. Analysts 13 Buy/1 Hold, avg PT $36.63. Below +15% tighten trigger. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum. Tech OK (1 loss). Limit <= +0.5% of ask, stop 8% below entry, target +16% (2:1). Skip if >+6% extended or spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%. Sector OK.
3. JPM add — Financials — big-bank follow-through; watch only.

### Risk Factors
- Cash 86.7%: Rule 12 gate forces >=1 add at open unless VIX >22 or futures gap < -2% — verify live
- CVE earnings Oct 29-30: gap risk
- 10Y ~5.25% + oil: valuation pullback risk; poor breadth
- Search data stale again: confirm futures/VIX via Alpaca quotes
- ClickUp env vars missing — no alert channel

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

## 2026-10-26 — Pre-market Research

### Account
- Equity: $97,578.52
- Cash: $84,954.22 (87.1%)
- Buying power: $375,164.92
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 26) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $32.37 | +$600.60 (+5.00%) | $30.4065 (trailing 10%, HWM $33.785) | 6.1% |

CVE GTC trailing stop confirmed live. Deployed 12.9% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found (stale results only) — check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: none verified; busy week ahead (Fed meeting, Trump–Xi, Honeywell spinoff, Amazon + mega-cap earnings)
- Earnings before open: none held (CVE ~Oct 29-30)

### Position News
- **CVE** ($32.37, +5.00%): no new news found; -1.6% Oct 23 close-to-now drift. Q3 ~Oct 29-30. Stop 6.1% away, -7% cut line ~$28.67. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over. Sector OK (1 verified loss). Limit <= +0.5% of ask, stop 8%, target +16%, R:R 2:1. Skip if spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%, R:R 2:1.
3. JPM add — Financials — limit order, spread check first; stop 8%, target +16%.
(Unverified today — no fresh catalyst search results; carried from Oct 23.)

### Risk Factors
- Cash 87.1%: Rule 12 gate applies at open unless VIX >22 or futures gap < -2%
- IEX-only quotes give wide spreads — limit orders near last trade, retry at midday
- Event-heavy week (Fed, Trump–Xi, earnings); CVE oil-sensitive, stop 6% away
- Search data stale: no live futures/VIX
- ClickUp env vars missing — no alert channel; no urgent items today

### Decision
TRADE (Rule 12 forced add; up to 2 positions, <=15% each, limit orders after live spread check; skip if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD CVE.

--- TRIMMED 2026-10-29 ---

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

--- TRIMMED 2026-10-28 ---
