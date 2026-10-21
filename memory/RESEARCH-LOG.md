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

## 2026-10-16 — Pre-market Research

### Account
- Equity: $98,270.31
- Cash: $71,071.51 (72.3%)
- Buying power: $360,442.68
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 12) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $31.92 | +$425.10 (+3.54%) | $29.862 (trailing 10%, HWM $33.18) | 6.5% |
| META | 20 | $755.722 | $737.50 | -$364.44 (-2.41%) | $694.143 (trailing 10%, HWM $771.27) | 5.9% |

Both GTC trailing stops confirmed live. Deployed 27.7% — far below 60% Rule-12 floor. No add executed since Oct 5.

### Market Context
- S&P 500 futures: no Oct 16 print found (searches stale) — unknown
- VIX: no fresh print found; last known ~15-16 — assume under 22 gate
- Today's catalysts: none verified; thin-catalyst week, yields/oil driving tape
- Earnings before open: none of CVE/META (CVE ~Oct 30 unconfirmed, META Oct 29)

### Position News
- **CVE** ($31.92, +3.54%): no new headlines; Q3 ~Oct 30; 13/14 analysts Buy, avg PT ~$36.67. HOLD
- **META** ($737.50, -2.41%): no verified new news. -7% cut line ~$702.8 (4.7% away). HOLD

### Trade Ideas
No catalyst-backed idea verified this pass (searches stale/undated; not fabricating entries). Rule-12 forced add still applies at market-open: fresh-catalyst search, add ≥1 position, ≤15% size, non-Technology preferred (Industrials / Healthcare / Financials). Sector status: none in EXIT.

### Risk Factors
- Deployment 27.7% under Rule-12 floor — cash drag vs benchmark
- META 5.9% from stop; yield pressure
- Oil/geopolitical volatility (CVE both ways)
- Data gaps: no live futures/VIX read; ClickUp credentials missing — no alerts possible

### Decision
TRADE (Rule 12 forced add, 1 position max, ≤15% sizing, limit order after live spread check at open; skip only if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD existing positions.

--- TRIMMED 2026-10-21 ---

## 2026-10-15 — Pre-market Research

### Account
- Equity: $98,448.61
- Cash: $70,972.11 (72.1%)
- Buying power: $360,822.64
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 12) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $33.15 | +$904.80 (+7.53%) | $29.862 (trailing 10%, HWM $33.18) | 9.9% |
| META | 20 | $755.722 | $727.40 | -$566.44 (-3.75%) | $694.143 (trailing 10%, HWM $771.27) | 4.6% |

Both GTC trailing stops confirmed live. Deployed 27.9% — far below 60% Rule-12 floor. No add executed Oct 12/13/14.

### Market Context
- S&P 500 futures: no Oct 15 print found (searches stale) — unknown
- VIX: no fresh print found; last known ~15-16 — assume under 22 gate
- Today's catalysts: no dated list surfaced; stocks trading off bonds (24-yr-high yields), oil firm, bank earnings season
- Earnings before open: none of CVE/META (META Oct 29, CVE Oct 29-30)

### Position News
- **CVE** ($33.15, +7.53%): no new headlines; Athabasca deal pending, Q3 ~Oct 30. HOLD
- **META** ($727.40, -3.75%): no verified new news; weak 2 days (-3.3%, -1.4% pre-mkt). -7% cut line ~$702.82 (3.4% away). HOLD, watch closely

### Trade Ideas
No catalyst-backed idea verified this pass (searches stale/undated; not fabricating entries). Rule-12 forced add still applies at market-open: run fresh-catalyst search, add ≥1 position, ≤15% size, non-Technology preferred (Industrials / Healthcare / Financials / Energy-adjacent). Sector status: none in EXIT. Week trades 0/3.

### Risk Factors
- Deployment 27.9% under Rule-12 floor — cash drag vs benchmark
- META 4.6% from stop, 3.4% from -7% cut; yield spike pressure
- US-Iran/oil volatility (CVE both ways)
- Data gaps: no live futures/VIX read
- ClickUp credentials missing — no alerts possible

### Decision
TRADE (Rule 12 forced add, 1 position max, ≤15% sizing, limit order after live spread check at open; skip only if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD existing positions.

--- TRIMMED 2026-10-20 ---
