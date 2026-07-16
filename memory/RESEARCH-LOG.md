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

## 2026-07-16 — Pre-market Research

### Account
- Equity: $106,273.15 | Cash: $58,107.05 (54.68%) | Deployed: $48,166.10 (45.32% — below 60% gate floor)
- Buying power: $367,293.29 (day-trade) / $164,380.20 (reg T)
- Daytrade count: not exposed by account endpoint; no same-day round trips, PDT not a concern
- Open positions: AMZN (86 sh), JPM (31 sh), OXY (285 sh) — 3/6 slots used
- Week trades: 1/3 (week of Jul 13) — 2 slots remain
- Overnight: equity up slightly from $106,112.27 (last close) to $106,273.15 (+0.15%)

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | HWM |
|--------|--------|-------|---------|----------------|------|-----|
| AMZN | 86 | $242.63 | $257.34 | +$1,265.16 (+6.06%) | $230.832 (10% trail) | $256.48 |
| JPM | 31 | $327.626129 | $348.16 | +$636.55 (+6.27%) | $314.622 (10% trail) | $349.58 |
| OXY | 285 | $54.960351 | $53.48 | −$421.90 (−2.69%) | $49.608 (10% trail) | $55.12 |

Cushions to stop: AMZN 10.3%, JPM 9.6%, OXY 7.2% — none close to breach.

### Market Context
- S&P 500 futures: −0.1% early Thursday, Polymarket implying only ~37% odds of an up open; S&P 500 closed Wed +0.38% at 7,572.40
- VIX: ~16.26 (range 15.88–16.57) — calm, well below the 22 gate threshold
- Today's catalysts: Crude topped $80/bbl overnight after Iran and the U.S. traded fresh attacks — bullish for OXY thesis but also pushing Treasury yields up and July Fed-hike odds higher; Fed Chair Kevin Warsh testifies to Congress today (hawkish-surprise risk); June retail sales, initial/continuing jobless claims, Philly Fed, NAHB housing index, business inventories, pending home sales all out today; SpaceX Starship test flight tonight (non-market catalyst)
- Earnings before open: UNH, TSM, GE Aerospace, ABT, AA, CFG, ISRG, PLD, STT, USB — none held; NFLX reports after close (Communication Services — EXIT sector, moot)

### Position News
- **AMZN** ($257.34, +6.06%): Record Prime Day spend cited as a driver of Wed's +3.25% pop; CEO Jassy says Trainium AI chip demand "very strong" on price/performance; AWS Compute/ML head Dave Brown departing end of July (Dave Treadwell takes over Aug 1) — leadership transition, not thesis-breaking; earnings Jul 30; stop cushion 10.3%; HOLD
- **JPM** ($348.16, +6.27%): Record Q2 (adj. net income $16.9B, GAAP $21.2B/$7.70 EPS vs $5.64 est., revenue $57.34B +27% YoY); Barclays raised PT to $420 from $391 (Overweight); $24M U.S. shipbuilding investment announced; stop cushion 9.6%; HOLD
- **OXY** ($53.48, −2.69%): Crude >$80/bbl overnight on fresh Iran-U.S. attacks — thesis intact, potential bounce catalyst today; Stephens cut PT to $69 (from $73, Jul 13) on pricing, still Overweight; Q2 report Aug 5; stop cushion 7.2%; HOLD, watch for oil-driven reaction at the open

### Trade Ideas
1. **UNH (Healthcare, watch-only)** — reports before open; sector OK (0 losses), no current exposure. No pre-positioning ahead of the print; enter only on a clear beat+raise with confirmed post-print strength.
2. **GE Aerospace (Industrials, watch-only)** — reports before open; sector untracked/OK, no current exposure. Same wait-and-react approach, no pre-positioning.
3. **OXY reaction to oil spike (maintenance, no slot used)** — crude >$80 on fresh overnight Iran-U.S. attacks strengthens the existing thesis; no new entry, let the existing 10% trail manage the move.

### Risk Factors
- Deployment 45.32% is below the 60% gate floor; VIX (~16.3) and futures (−0.1%) do not meet the rule-12 exception (VIX>22 or gap<-2%) — expect the market-open workflow to need to resolve the gate against a heavy earnings/Fed-testimony day
- Crude >$80/bbl on fresh overnight Iran-U.S. attacks — supports OXY but is headline-driven and could reverse fast; also lifting yields/Fed-hike odds, a risk-off cross-current for the broader tape
- Fed Chair Kevin Warsh testifies to Congress today — hawkish-surprise risk given already-rising rate-hike expectations
- Heavy earnings slate before open (UNH, TSM, GE, ABT, AA, CFG, ISRG, PLD, STT, USB) plus NFLX after close — premarket/intraday volatility risk, none held directly
- Technology and Communication Services remain sector-EXIT — no new buys regardless of TSM/NFLX results

### Decision
HOLD (pre-market) — no confirmed post-earnings reaction yet to act on; defer entry decision to market-open workflow, which will also need to resolve the deployment-gate trigger (45.32% deployed, no VIX/gap exception) against today's heavy earnings/Fed-testimony calendar. Week trades 1/3 — 2 slots remain.

**Environment note:** CLICKUP_API_KEY/CLICKUP_WORKSPACE_ID/CLICKUP_CHANNEL_ID missing from env this run — console-only, no ClickUp notification sent. No urgent items today regardless (all positions within stop bands, no thesis breaks).

## 2026-07-15 — Pre-market Research

### Account
- Equity: $105,717.58
- Cash: $58,107.05 (54.96%) | Deployed: $47,610.53 (45.04% — below 60% gate floor)
- Buying power: $365,737.70 (day-trade) / $163,824.63 (reg T)
- Daytrade count: 0
- Open positions: AMZN (86 sh), JPM (31 sh), OXY (285 sh) — 3/6 slots used
- Week trades: 1/3 (week of Jul 13) — 2 slots remain

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop |
|--------|--------|-------|---------|----------------|------|
| AMZN | 86 | $242.63 | $249.33 | +$576.35 (+2.76%) | $227.27 (10% trail) |
| JPM | 31 | $327.63 | $344.00 | +$507.59 (+5.00%) | $310.23 (10% trail) |
| OXY | 285 | $54.96035 | $54.40 | −$159.70 (−1.02%) | $49.608 (10% trail) |

### Market Context
- S&P 500 futures: +0.11% — cooler June CPI (headline −0.4% m/m, YoY 3.5% vs 3.8% est.) cut July Fed-hike odds to 17% (from 42%)
- VIX: ~16.5 (down ~3.9% Jul 14 close), range 16.15–17.56 — well below the 22 gate threshold
- Today's catalysts: PPI, EIA crude inventories, Empire State Manufacturing, MBA mortgage apps; cooling inflation supporting risk appetite; Brent crude still >$84/bbl on continued U.S.-Iran strikes — bullish backdrop for OXY thesis, risk-off wildcard for broader tape
- Earnings before open: JNJ, MS, BK, PNC, ASML, Progressive, Cintas, JB Hunt, United Airlines, Elevance Health, Kinder Morgan — none held; JPM (held) already reported Q2 beat yesterday ($6.14 EPS vs $5.85 est., $58.02B rev vs $50.19B est.) but dipped slightly premarket (sell-the-news)

### Position News
- **AMZN** ($249.33, +2.76%): No new catalyst overnight; AI capex bond sale / AWS deals thesis intact; stop cushion 8.9%; HOLD
- **JPM** ($344.00, +5.00%): Q2 beat on both lines yesterday, stock dipped slightly premarket (sell-the-news, not thesis-breaking); stop cushion 9.9%; HOLD
- **OXY** ($54.40, −1.02%): Stephens cut PT to $69 (from $73), mixed vs. other analysts still constructive; oil elevated on continued Iran strikes keeps thesis intact; stop cushion 8.8%; HOLD

### Trade Ideas
1. **Financials earnings reaction (watch-only)** — MS, BK, PNC report before open; Financials sector 0 losses, JPM already held and beat cleanly yesterday. No pre-committed entry; would only add on a clean beat+raise with confirmed post-print strength (avoid chasing a gap). Stop 7-10% below entry, target min 2:1.
2. **JNJ (Healthcare, watch-only)** — reports before open, sector has 0 losses and no current exposure. No pre-positioning ahead of the print; enter only on a clear beat+raise with volume confirmation.
3. **Energy add-on (contingent)** — Iran strikes continuing, Brent >$84 keeps sector momentum intact, but OXY is the only position and Stephens just trimmed its PT; no second energy name identified with a clean catalyst today — hold at one position, reassess after PPI/inventories data.

### Risk Factors
- Deployment 45.04% is below the 60% gate floor; VIX (~16.5) and futures (+0.11%) do not meet the rule-12 exception (VIX>22 or gap<-2%) — expect the market-open workflow to require adding ≥1 position today
- Brent >$84/bbl on continued U.S.-Iran strikes — supports OXY but is headline-driven and could reverse fast either direction
- Heavy earnings slate (JNJ, MS, BK, PNC, ASML, UAL, etc.) — premarket/open volatility risk across sectors, none held directly except JPM (already reported)
- Tech and Communication Services remain sector-EXIT — no exposure, no action needed

### Decision
HOLD (pre-market) — no confirmed post-earnings reaction yet to act on; defer entry decision to market-open workflow, which will also need to resolve the deployment-gate trigger (45.04% deployed, no VIX/gap exception).

**Environment note:** CLICKUP_API_KEY/CLICKUP_WORKSPACE_ID/CLICKUP_CHANNEL_ID missing from env this run — console-only, no ClickUp notification sent.

--- TRIMMED 2026-07-16 ---

## 2026-07-10 — Pre-market Research

### Account
- Equity: $106,835.22 | Cash: $34,057.74 (31.88%) | Deployed: $72,777.48 (68.13% — below 75–85% target, above 60% gate floor)
- Buying power: $340,007.89 (day-trade) / $140,892.96 (reg T) | Daytrade count: 0
- Open positions: AMZN (86 sh), JPM (31 sh), LLY (13 sh), NVO (513 sh) — 4/6 slots used
- Week trades: 0/3 (week of Jul 6) — 3 slots remaining
- Phase P&L: +$6,835.22 (+6.84%) | Day 33, Friday
- Overnight: equity up slightly from $106,598.54 (last close) to $106,835.22 (+0.22%)

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | HWM |
|--------|--------|-------|---------|----------------|------|-----|
| AMZN | 86 | $242.63 | $247.28 | +$399.93 (+1.92%) | $227.27 (10% trail) | $252.53 |
| JPM | 31 | $327.63 | $336.40 | +$271.99 (+2.68%) | $309.10 (10% trail) | $343.45 |
| LLY | 13 | $1,078.65 | $1,219.51 | +$1,831.18 (+13.06%) | $1,148.13 (7% trail) | $1,234.55 |
| NVO | 513 | $41.27 | $49.18 | +$4,056.75 (+19.16%) | $48.35025 (5% trail) | $50.895 |

**LLY +20% tighten trigger**: $1,294.38; current $1,219.51 — gap $74.87 (5.8% away), not close; 7% trail active since Jul 8 crossing.
**NVO cushion to stop**: 5% trail stop $48.35025 vs current $49.18 — $0.83 (1.7%) above the live GTC stop; already tightest (5%) tier, no manual action, GTC will fire automatically if breached.

### Market Context
- S&P 500 futures: −0.22% early Friday — Polymarket implying only ~20% odds of an up open; caution on geopolitical backdrop and elevated inflation risk despite cooling oil after Trump said Iran signaled openness to negotiate
- VIX: ~16.1 (opened 16.58, intraday range 15.93–17.27) — calm, well below the 22 gate threshold
- Today's catalysts:
  - **Delta (DAL) earnings before open** — first real travel-demand read this week; not held
  - **Fresh overnight attacks by both sides in the Strait of Hormuz** — stocks climbing anyway Thursday on hopes it doesn't escalate to full-scale war; headline risk remains elevated into the weekend
  - **AI-driven optimism continuing**: chip stocks led Thursday's rally, brushing aside Middle East flare-up — Tech remains EXIT, no direct exposure
  - **10-yr Treasury yield ~4.58%**, sticky inflation signals — keeping a lid on any serious rally alongside firmer oil/crude
- Earnings before open: DAL (not held); none for portfolio names (JPM Jul 14, AMZN Jul 30)

### Position News
- **AMZN** ($247.28, +1.92%): Plans to borrow additional $25B for data-center/AI capex; Goldman raised AWS capex estimate to $827B (2026–2028) on AI demand/supply imbalance; "Moonraker" Alexa+ upgrade project running more costly than expected; stock flatlined YTD with NVDA despite AI trade; earnings Jul 29; stop $227.27 (cushion 8.9%); HOLD
- **JPM** ($336.40, +2.68%): Traded $330.13–338.68 Jul 9, closed $330.90; Q2 earnings Jul 14 (EPS est. $5.52, +11.3% YoY; revenue est. $48.71B, +8.4%), estimate revised up 1.3% in past 30 days; +7% past month vs S&P +1.1%, Zacks Rank #2 Buy; new small-company dealmaking team announced; stop $309.10 (cushion 8.1%); HOLD
- **LLY** ($1,219.51, +13.06%): Near all-time highs on obesity/diabetes (Mounjaro/Zepbound) demand; 4h chart bullish, trading above all major moving averages; +20% tighten trigger 5.8% away, not urgent; stop $1,148.13 (cushion 5.9%); HOLD
- **NVO** ($49.18, +19.16%): Oral Wegovy prescription-growth slowdown flagged ahead of earnings (Aug 4, consensus $0.68); CagriSema device study halted, refocusing investors on core obesity assets; exec Camilla Sylvest departed to a competitor board; HSBC PT raised to DKK 300 (Jul 6, Hold); DKK 15B buyback ongoing; cushion to 5% stop 1.7%, still tightest in the portfolio; HOLD

### Trade Ideas
1. **DAL (Delta), Industrials — watch only**: Earnings before open today, first travel-demand read of the week; not held, no pre-positioning ahead of the print — wait and react to the result.
2. **AI/chip rebound (Tech) — no action**: Thursday's rally led by semis continues into today's tone, but Tech remains EXIT (2 consecutive losses) — no entry regardless of momentum.
3. **Hold slot**: Deployed 68.13% — below 75–85% target but above the 60% gate floor, so no forced add. No clean, catalyst-backed setup in an open sector today; wait for a better entry (0/3 trades used this week).

### Risk Factors
- **Strait of Hormuz attacks overnight (both sides)** — elevated Middle East headline risk into the weekend, could reverse the "de-escalation" narrative fast
- **Sticky inflation / 10-yr yield ~4.58%** — capping upside even as oil cools on negotiation hopes
- **NVO cushion to its 5% trailing stop only 1.7%** — no manual action needed, GTC already at tightest tier
- **LLY 5.8% from its +20% tighten trigger** — not urgent, keep watching
- Deployed 68.13% below 75–85% target, above 60% gate floor — not forced to add
- Technology + Communication Services remain EXIT sectors — no new buys despite AI/chip rebound
- Consumer Staples has 1 consecutive loss (WMT) — one more loss triggers EXIT
- **Environment note**: CLICKUP_API_KEY/CLICKUP_WORKSPACE_ID/CLICKUP_CHANNEL_ID missing from env this run — ClickUp alerting unavailable; no urgent items today regardless (all positions green, no stop breaches, no thesis breaks)

### Decision
HOLD — Default patience. Deployed 68.13% is below the 75–85% target but above the 60% gate floor, so no forced add. Overnight Strait of Hormuz attacks and sticky inflation argue against chasing a new position; AI/chip rebound sits in the EXIT Tech sector anyway. Priority today: watch Delta's earnings print for a travel-demand read, and keep an eye on NVO's 1.7% cushion to its 5% trail. Week trades 0/3 — full 3 slots available.

## 2026-07-13 — Pre-market Research

### Account
- Equity: $106,405.11 | Cash: $34,057.74 (32.00%) | Deployed: $72,347.37 (67.99% — below 75–85% target, above 60% gate floor)
- Buying power: $338,803.59 (day-trade) / $140,462.85 (reg T) | Daytrade count: 0
- Open positions: AMZN (86 sh), JPM (31 sh), LLY (13 sh), NVO (513 sh) — 4/6 slots used
- Week trades: 0/3 (new week of Jul 13) — 3 slots remaining
- Phase P&L: +$6,405.11 (+6.41%) | Day 34, Monday
- Overnight: equity essentially flat, $106,422.33 (last close) to $106,405.11 (-0.02%)

### Positions
| Ticker | Shares | Entry | Current | Unrealized P&L | Stop | HWM |
|--------|--------|-------|---------|----------------|------|-----|
| AMZN | 86 | $242.63 | $245.78 | +$270.90 (+1.30%) | $227.27 (10% trail) | $252.53 |
| JPM | 31 | $327.63 | $336.99 | +$290.28 (+2.86%) | $309.10 (10% trail) | $343.45 |
| LLY | 13 | $1,078.65 | $1,189.00 | +$1,434.55 (+10.23%) | $1,148.13 (7% trail) | $1,234.55 |
| NVO | 513 | $41.27 | $49.33 | +$4,134.01 (+19.53%) | $48.35025 (5% trail) | $50.895 |

**LLY +20% tighten trigger**: $1,294.38; current $1,189.00 — gap $105.38 (8.9% away), not close; 7% trail active.
**LLY cushion to stop**: $1,189.00 vs stop $1,148.13 — $40.87 (3.4%) above the live GTC stop; narrowed from 5.9% Friday after a pullback — no manual action, watch closely.
**NVO cushion to stop**: $49.33 vs stop $48.35025 — $0.98 (2.0%) above the live GTC stop; already tightest (5%) tier, no manual action.

### Market Context
- S&P 500 futures: −0.51% premarket Monday — weekend Iran-US military escalation, IRGC attacked a commercial ship transiting the Strait of Hormuz, shattering the interim ceasefire; betting markets pricing only ~22% odds of an up open
- VIX: last close 15.03 (Jul 10, −5.11%); no live premarket print found, but likely rising given the weekend escalation — still well below the 22 gate threshold based on Friday's level
- Today's catalysts: no major data/earnings Jul 13 itself; heavy week ahead — CPI + Fed Chair Warsh testimony + big-bank earnings (JPM, BAC, GS, WFC, C) Tue Jul 14; PPI + Fed Beige Book + earnings (ASML, JNJ, MS, BLK) Wed Jul 15; TSMC, GE Aerospace, UNH, NFLX Thu Jul 16; energy prices climbing again on the broken ceasefire
- Earnings before open: none today for held names; JPM reports tomorrow Jul 14 pre-market (EPS est. $5.61 vs $4.96 YoY, revenue est. $49.56B vs $44.91B)

### Position News
- **AMZN** ($245.78, +1.30%): $25B bond sale launched to fund AI infra capex (~$200B 2026 run-rate); Leo satellite network past 390 deployed sats; Q2 earnings Jul 30 (EPS est. $1.82, rev est. $196.02B); stop $227.27 (cushion 7.5%); HOLD
- **JPM** ($336.99, +2.86%): Q2 earnings tomorrow Jul 14 pre-market; board raised dividend to $1.65/qtr and authorized new $50B buyback effective Jul 1; KBW raised PT to $370 from $363 (Jul 9); Buy consensus PT $350 (17 analysts); stop $309.10 (cushion 8.3%); HOLD — no pre-positioning ahead of print
- **LLY** ($1,189.00, +10.23%): Near record highs on Mounjaro/Zepbound demand; JPMorgan's Schott raised PT to $1,400 from $1,300; +20% tighten trigger 8.9% away, not urgent; cushion to 7% stop narrowed to 3.4% after pullback; HOLD
- **NVO** ($49.33, +19.53%): Medicare began covering GLP-1 obesity drugs Jul 1 (tailwind); DKK15B buyback ongoing (treasury stake 0.9%); FRONTIER4 denecimib phase-3 data out, CagriSema device study halted; analysts still cautious on FY26 guide; cushion to 5% stop only 2.0% — tightest in portfolio, unchanged; HOLD

### Trade Ideas
1. **Energy (watch only, contingent on multi-day confirmation)**: Oil spiking on the broken Iran ceasefire/Strait of Hormuz attack; sector untouched (0 losses, open). Single-day geopolitical spike, not a trend — no entry today, wait for multi-day confirmation.
2. **JPM earnings (maintenance — no slot used)**: Reports tomorrow pre-market with a real expected move; no size adjustment ahead of the print, let the existing 10% trail do its job either direction.
3. **Hold slot**: Deployed 67.99% — below 75–85% target but above the 60% gate floor, so no forced add. No clean, catalyst-backed setup in an open sector today; an actual (not just rhetorical) Iran-US military clash argues for patience into a data/earnings-heavy week.

### Risk Factors
- **Weekend Iran-US military escalation**: IRGC attacked a commercial ship in the Strait of Hormuz, shattering the ceasefire — S&P futures −0.51%, ~22% odds of an up open; energy prices climbing again; a materially bigger event than prior days' headline tension, though still no direct portfolio exposure
- **LLY cushion to its 7% trailing stop narrowed to 3.4%** ($40.87) after a pullback from Friday's close — no manual action, GTC will fire automatically if breached, but watch closely
- **NVO cushion to its 5% trailing stop only 2.0%** — tightest margin in the portfolio, unchanged risk profile
- **JPM reports Q2 earnings tomorrow pre-market** — no pre-positioning, but expect a real move within 24h
- Deployed 67.99% below 75–85% target, above 60% gate floor — not forced to add
- Technology + Communication Services remain EXIT sectors — no new buys
- **Environment note**: CLICKUP_API_KEY/CLICKUP_WORKSPACE_ID/CLICKUP_CHANNEL_ID missing from env this run — ClickUp alerting unavailable; no stop breaches or thesis breaks today, but flagging the Iran/Hormuz escalation directly since ClickUp can't

### Decision
HOLD — Default patience. Deployed 67.99% is below the 75–85% target but above the 60% gate floor, so no forced add. This weekend's actual Iran-US military clash in the Strait of Hormuz (ceasefire broken, not just rhetoric) is a materially bigger risk event than prior headline tension, landing right before a heavy week of CPI, bank earnings (including our own JPM tomorrow), and PPI — no new positions until the dust settles. Priority today: watch JPM's Tue print and LLY's narrowing 3.4% stop cushion after its pullback. Week trades 0/3 — full 3 slots available (new week of Jul 13).

## 2026-07-14 — Pre-market Research

### Account
- Equity: $105,398.18 | Cash: $73,770.85 (70.0%) | Deployed: $31,627.33 (30.0% — well below 60% gate floor, DEPLOYMENT GATE TRIGGERED)
- Buying power: $383,639.92 (day-trade) / $179,169.03 (reg T)
- Daytrade count: not exposed by account endpoint; no same-day round trips today, PDT not a concern
- Open positions: AMZN (86 sh), JPM (31 sh) — 2/6 slots used
- Week trades: 0/3 (week of Jul 13) — 3 slots remaining
- **LLY and NVO both stopped out via GTC trailing stop at market open today** (~9:35 AM ET): LLY 13 sh filled $1,148.02 (+6.43% vs $1,078.65 entry; 7% trail off HWM $1,234.55, order 5ccf23ab); NVO 513 sh filled $48.321345 (+17.09% vs $41.27 entry; 5% trail off HWM $50.895, order e1c950f4). Both profitable exits, not losses — Healthcare sector Consecutive Losses stays at 0.

### Market Context
- S&P 500 futures: -0.2% premarket, Nasdaq mixed/slightly higher — traders cautious into a heavy bank-earnings/CPI morning. Not a >-2% gap.
- VIX: 17.16 (+14.17% overnight) — still inside the 12-20 "MID" band, below the 22 gate-exception threshold.
- Today's catalysts: Cooler CPI (headline +3.5% y/y vs +3.8% expected) → bond yields down; US enforces a Strait of Hormuz naval blockade starting 4pm ET today (20% toll on all cargo) after the Jun 17 ceasefire fully collapsed and US forces bombed 80+ targets in Iran over the weekend; Brent/WTI both jumped ~8% Jul 13 to ~$82/$77, ~230 loaded tankers stuck in the Gulf; IBM -20% premarket on an earnings miss (Tech — EXIT sector, no impact); AMD PT raised by Wolfe.
- Earnings before open: JPM (held) reported record Q2 — net income $21.2B ($7.70 GAAP EPS incl. one-timers; $6.14 core EPS beat $5.74 est by $0.40), revenue $57.3B vs $49.9B est, every business line record. Big-bank earnings sweep continues rest of week (BAC, GS, WFC, C).

### Trade Ideas
1. **OXY (Occidental Petroleum) — Energy, new sector entry**: Catalyst = Strait of Hormuz blockade enforcement begins today 4pm ET (20% cargo toll), 2nd consecutive day of escalation (Jul 13: XOM +4.43%, CVX +3.16%, OXY +3.65%), satisfying prior "wait for multi-day confirmation" caution; Evercore ISI upgraded OXY to Outperform Jul 7; consensus PT $57-65 (10-18% upside), high $75. Entry ~$55.05, stop 10% trail GTC (~$49.55 initial ref), target $66 (+20%), R:R 2:1. XOM/CVX quotes showed erratic 5-9% bid/ask spreads (data-quality issue, confirmed on two separate pulls) — both skipped; OXY quote stayed clean/tight ($55.04/$55.07) on both pulls.
2. **JPM add (maintenance, no slot used)**: Record Q2 beat, but position already held and up post-earnings — no new entry, let the existing 10% trail manage the move.
3. **Healthcare re-entry (LLY/NVO) — deferred, no slot used**: Both stopped out at open on profitable trailing stops. LLY thesis still strong (UBS raised PT to $1,425, Guggenheim to $1,273, shares near ATH) but no same-day re-chase right after a stop fill — wait for a fresh setup. NVO shows an emerging thesis crack (CagriSema device study halted, some analysts flagging 10% downside) — skip for now, not a clean re-entry.

### Risk Factors
- **Deployment gate breach**: deployed 30.0%, well below the 60% floor after two large stop-outs — forces ≥1 new position today per Strategy rule 12 (neither VIX>22 nor futures gap<-2% exception applies).
- **US-Iran escalation live and worsening**: Hormuz blockade enforcement begins 4pm ET today; ~230 loaded tankers stuck in the Gulf; genuine tail-risk event, though OXY/energy is a direct beneficiary here, not a risk to the existing book.
- **XOM/CVX data quality**: erratic wide quotes on both, confirmed on repeat pulls — avoided both, used OXY (clean, stable book) instead.
- Technology and Communication Services remain sector-EXIT — no new buys there (moot today — IBM miss/SK Hynix weakness confirm avoiding tech regardless).
- **Environment note**: CLICKUP_API_KEY/CLICKUP_WORKSPACE_ID/CLICKUP_CHANNEL_ID missing from env this run — ClickUp alerting unavailable; flagging the deployment-gate trade and Hormuz escalation directly here since ClickUp can't.

### Decision
TRADE — Deployment gate forces action (30.0% deployed vs 60% floor, no VIX/futures exception). Buy OXY (Energy, new sector) on Hormuz blockade escalation, now Day 2 confirmed with a hard enforcement mechanism kicking in this afternoon. Skip Healthcare re-entry despite two profitable stop-outs today — no same-day re-chase, and NVO shows an emerging thesis crack. Week trades 0/3 before this trade, becomes 1/3 after.
