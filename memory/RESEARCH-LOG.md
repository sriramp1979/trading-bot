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

## 2026-10-14 — Pre-market Research

### Account
- Equity: $99,121.31
- Cash: $70,972.11 (71.6%)
- Buying power: $362,706.20
- Daytrade count: 0 (not flagged by API)
- Week trades: 0/3 (week of Oct 12) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $33.00 | +$846.30 (+7.04%) | $29.55 (trailing 10%, HWM $32.84) | 10.5% |
| META | 20 | $755.722 | $763.96 | +$164.76 (+1.09%) | $694.14 (trailing 10%, HWM $771.27) | 9.1% |

Both GTC trailing stops confirmed live. Deployed 28.4% — far below 60% Rule-12 floor. No add executed Oct 12/13 despite Oct 13 plan.

### Market Context
- S&P 500 futures: no Oct 14 print found (search returned stale results) — treat as unknown; S&P last record close ~7,811 (Oct 9)
- VIX: no fresh print found; last known ~15-16 — assume well under 22 gate
- Today's catalysts: no dated list surfaced; bank earnings season, oil (Brent >$100)/US-Iran headlines, 24-yr-high Treasury yields; breadth poor at highs
- Earnings before open: none of CVE/META (META Oct 29, CVE Oct 29-30)

### Position News
- **CVE** ($33.00, +7.04%): Athabasca Oil acquisition (C$5.7B EV, announced Oct 5, close Dec); oil strength tailwind. HOLD, trail tightens at +15%
- **META** ($763.96, +1.09%): no new news; Q3 earnings Oct 29. HOLD

### Trade Ideas
No catalyst-backed idea verified this pass (searches stale/undated; not fabricating entries). Rule-12 forced add still applies at market-open (no VIX>22 / gap<-2% evidence): market-open must run a fresh-catalyst search and add ≥1 position, ≤15% size, non-Technology preferred (Energy-adjacent / Industrials / Healthcare / Financials). Sector status: none in EXIT. Week trades 0/3.

### Risk Factors
- Deployment 28.4% under Rule-12 floor — cash drag vs benchmark
- Rates/yield spike pressure on META
- US-Iran/oil volatility (CVE event risk both ways)
- Data gaps: no live futures/VIX read this run
- ClickUp credentials missing — no alerts possible

### Decision
TRADE (Rule 12 forced add, 1 position max, ≤15% sizing, limit order after live spread check at open; skip only if futures gap < -2% or VIX > 22). 10% trailing GTC stop immediately after fill. HOLD existing positions.

--- TRIMMED 2026-10-19 ---

## 2026-10-13 — Pre-market Research

### Account
- Equity: $98,224.81
- Cash: $70,972.11 (72.3%)
- Buying power: $360,196
- Daytrade count: 0 (not flagged by API; no day trades in log)
- Week trades: 0/3 (week of Oct 12) — 3 slots available

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | Cushion to stop |
|--------|--------|-------|---------|----------------|------|------------------|
| CVE | 390 | $30.83 | $31.93 | +$429.00 (+3.57%) | $29.25 (trailing 10%, HWM $32.50) | 8.4% |
| META | 20 | $755.722 | $740.00 | -$314.44 (-2.08%) | $685.197 (trailing 10%, HWM $761.33) | 7.4% |

Both GTC trailing stops confirmed live. Deployed 27.7% — far below 60% Rule-12 floor.

### Market Context
- S&P 500 futures: no same-day data found via search (stale results only). Last known: S&P 500 7,811.54 on Oct 9 (+0.59%), near record; breadth poor. Check live at open
- VIX: no same-day reading found; last known ~15-16 — assume <22 gate
- Today's catalysts: no dated list found. 10Y yield ~5.25% (24-yr highs), oil spike early Oct, Iran/Hormuz overhang; telecom rout Oct 9 (TMUS -13%, T -10%); Q3 bank earnings ramping
- Earnings before open: none held (META ~Oct 28, CVE Oct 29)

### Position News
- **CVE** ($31.93, +3.57%): Athabasca deal (C$5.7B EV, close Dec 2026) digestion; energy led sectors Oct 8. No new news. Cushion 8.4%. HOLD
- **META** ($740.00, -2.08%): No new news; capex ($125-145B) concern into ~Oct 28 earnings. No thesis break. HOLD

### Trade Ideas
1. QCOM — Technology — AI/semis momentum carry-over (unfilled since Oct 5). Tech OK (INTC loss = 1). Limit ≤ +0.5% of ask, stop 8% below entry, target +16% (2:1). Skip if >+6% extended or spread >1%.
2. MRNA — Healthcare — Nasdaq-100 inclusion carry-over. Spread <1% required; stop 8%, target +16%. Sector OK.
3. JPM-adjacent financials add — Financials — big-bank Q3 reactions; watch only, not actionable pre-open.

### Risk Factors
- Cash 72.3%: Rule 12 gate forces ≥1 add at open unless VIX >22 or futures gap < -2% — verify live
- 10Y ~5.25% + oil: tech/valuation pullback risk; index near records with poor breadth
- Search data stale again: confirm futures/VIX via Alpaca quotes
- META capex narrative; CVE deal digestion
- ClickUp env vars missing — no alert channel; no urgent items

### Decision
TRADE (Rule 12 forced add, 1 position max, ≤15% sizing, limit order after live spread check). Prefer QCOM or MRNA; HOLD instead if futures gap < -2% or VIX >22. Real 10% trailing GTC stop immediately after fill.
