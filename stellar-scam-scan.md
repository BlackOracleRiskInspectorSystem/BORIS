# BORIS — Soroban Intelligence Module (SIM)
**Target:** Stellar / Soroban ecosystem — batch scan
**Scan date:** 2026-03-02
**Watchlist:** 358 assets
**Engine:** BORIS beta 1.3 — SIM module

---

## Discovery Run

```
Sources scanned:
  Top assets:         0 new
  Active pairs:       0 new
  Recent trades:     92 new  ← primary source
  Soroban contracts:  0 new
  DeFi protocols:     0 new

Total watchlist after discovery: 358 assets
```

---

## Scam Detection — Batch Results

```
Analyzed:    358 assets
💀 Confirmed:  52 scams
🏭 Factories:   2 scam factory networks
```

### Scam Factories

```
🏭 xlmassets.com — 5 confirmed tokens
   ADA · AVAX · BCH · BNB · BTC

   Pattern: Mass-mints fake major crypto tokens on Stellar.
   Issuer creates dozens of assets impersonating known tickers.
   No actual backing. Designed to trap users expecting real assets.

🏭 vanguardstellar.org — 7 confirmed tokens
   AMZN · BND · BRKB · GOOGL · JNJ · META · NVDA

   Pattern: Fake tokenized stocks on Stellar.
   Impersonates Vanguard ETFs and equity securities.
```

### Confirmed Scams — Score 100

```
💀 ADA    TOKEN IMPERSONATION        [xlmassets.com]
💀 AMZN   TOKEN IMPERSONATION        [vanguardstellar.org]
💀 BTC    FACTORY IMPERSONATION      [xlmassets.com]
💀 ETH    FACTORY IMPERSONATION      [xlmassets.com]
💀 LINK   FACTORY IMPERSONATION      [xlmassets.com]
💀 NVDA   FACTORY IMPERSONATION      [vanguardstellar.org]
💀 SOL    FACTORY IMPERSONATION      [xlmassets.com]
💀 SUI    FACTORY IMPERSONATION      [xlmassets.com]
💀 TSLA   FACTORY IMPERSONATION      [vanguardstellar.org]
💀 USDT   FACTORY IMPERSONATION      [xlmassets.com]
```

### Score 75–90 (Scam Factory Network)

```
💀 TRX    90  SCAM FACTORY  [xlmassets.com]
💀 WBTC   90  SCAM FACTORY  [xlmassets.com]
💀 XRP    90  SCAM FACTORY  [xlmassets.com]
💀 DOGE   75  SCAM FACTORY  [xlmassets.com]
💀 SHIB   75  SCAM FACTORY  [xlmassets.com]
💀 USD1   75  SCAM FACTORY  [xlmassets.com]
💀 XLM    70  TOKEN IMPERSONATION     (native XLM clone)
```

### Score 50–55 (Likely Scam)

```
txsestellar.org cluster — 16 tokens:
  LUMI · MGDL · MTRX · NVPT · NXSN · ORL · POLI
  PTNR · SHFL · STRS · TASE · TSEM + more

usastocks.net cluster — 4 tokens:
  SWISSGOLD · USD · XAU · XPLA
```

---

## Asset Deep Scans — Selected Examples

### 3qualiT — CRITICAL: Oracle Manipulation Surface

```
Trustlines: 4
Supply:     33,291,473,886
Volume 24h: $6.15
Orderbook:  0 bids / 0 asks

Oracle:     VWAP from SDEX (single source)
Sanity:     NONE
Circuit:    NONE
Cost 100x:  $0.00
```

```
🚨 ORACLE MANIPULATION SURFACE — YieldBlox-Class Vulnerability

Single-source VWAP oracle reads from market with $0.00 ask depth.
Cost to move price 100x: $0.00.
No sanity check. No circuit breaker.
Exploitable as collateral in any lending protocol.

DO NOT use as lending collateral.
```

### AMERICANGOLD — CRITICAL + Clawback

```
Trustlines: 130
Volume 24h: $0.00
Last trade: 8,577h ago (357 days)
Flags:      auth_revocable · clawback

Oracle:     VWAP from SDEX — reads DEAD market
Cost 100x:  $0.00
```

```
🚨 Oracle reads from dead market
   Last trade 357 days ago.
   Single manipulated trade becomes the truth.

🔴 Issuer Has Clawback Authority
   Can confiscate tokens from any holder.

🟡 Issuer Can Freeze Trustlines
   auth_revocable=true
```

### AQUA — Elevated Risk (healthiest asset in scan)

```
Trustlines: 189,204
Volume 24h: $262.73
Spread:     0.18%
Traders 24h: 51 (top: 26%)

Oracle Risk: 60/100 (single source, no circuit breaker)
Overall:     41/100 — ELEVATED RISK
```

```
Even the "best" asset in this scan has:
- Single-source VWAP oracle
- No sanity validation
- No circuit breaker
- Extreme bid/ask asymmetry ($9.55 bid vs $665K ask)
```

### AMM — $191 to move price 100x

```
Spread:    197.7% — market non-functional
Cost 100x: $191.35

🚨 Oracle Manipulation Trivially Cheap
   Any VWAP oracle reading this market is exploitable.
   $191 is within reach of any casual attacker.
```

---

## Oracle Risk Pattern — Ecosystem-Wide

```
Finding across 358 assets scanned:

Single-source VWAP oracle (Reflector):  ~95% of assets
No sanity validation:                   ~95% of assets
No circuit breaker:                     ~95% of assets
Cost to move price 100x = $0.00:        majority of assets

This is not a per-asset bug.
This is a structural property of the Stellar/Soroban ecosystem
when SDEX is used as the sole oracle source.

Any lending protocol using Reflector oracle against these assets
is exposed to YieldBlox-class oracle manipulation.
```

> **YieldBlox incident reference:** In 2022, YieldBlox (Stellar) was exploited
> via oracle manipulation on a thin SDEX market. Same vulnerability class
> remains present across the majority of Stellar assets.

---

## Radar Settings

```
scan_interval_min:        15
alert_new_critical:       true
alert_manip_drift_pct:    50%
alert_depth_drift_pct:    60%
alert_volume_collapse_pct: 80%
worker_threads:           3
max_history_days:         90
```

---

*BORIS beta 1.3 — SIM module | Stellar/Soroban Intelligence*
*Not investment advice. Not "scam / not scam". BORIS maps structure.*
