# BORIS — Market Detection Engine
**Target:** Token — *ticker redacted*
**Scan date:** 2026-03-02
**Engine:** BORIS beta 1.3 — Market Engine
**Scans:** 4 over 17.3h (temporal tracking)

---

## Market Snapshot

```
Price:    $3.53
MCap:     $165.2M
Vol 24h:  $6.7M
Δ 24h:    +4.4%
Δ 7d:     +24.0%
Δ 30d:    +32.8%
Age:      1,942 days
Circ:     48% of total supply
```

---

## Risk Score

```
Overall:      50/100 — HIGH
Manipulation: 36/100
Fundamental:  78/100
Overcrowding:  0/100
Organic prob: 41/100
```

---

## Derivatives

```
OI (Binance):  $3.2M
OI (Bybit):    $1.4M
OI total:      $4.5M
OI Δ24h:       -8.3%
OI Δ7d:        -2.8%
OI velocity:    0.5x vs baseline

OI/Vol ratio:   0.47x

Funding (Binance):  0.000050
Funding (Bybit):   -0.000320   ← divergence
Funding trend:      stable
Funding avg 7d:     0.000026

Longs:    43% retail accounts
          60% top traders  (+17% divergence — smart money vs retail)
L/S BB:   33% long

Taker:    53% buy pressure

Orderbook depth 2%:  $122,500
Depth imbalance:     1.36x

OI/Depth ratio:      26x  ← CRITICAL
```

---

## Signals

### 🔴 OI/FuturesDepth 26x — Squeeze Guaranteed on Move
```
OI total: $4.5M
Depth 2%: $122,500

Ratio: 26x

Interpretation:
  Futures positions are 26x larger than the orderbook depth
  that would need to absorb liquidation cascades.

  On any significant price move:
  → Liquidations trigger
  → Orderbook cannot absorb
  → Cascade amplifies the move

  Direction unknown. Size of move is not.
  This is a squeeze setup regardless of direction.
```

### 🟠 GitHub — Last Push 444 Days Ago
```
Score contribution: +20

Last commit: 444 days ago
Active repos found: 3

Interpretation:
  Development activity has stopped.
  Price is +24% in 7 days with no development signal.
  Price movement is not driven by product updates.

  This does not mean collapse is imminent.
  It means the price driver is not fundamental.
```

### 🟡 Supply — 48% Circulating
```
Score contribution: +6

52% of total supply is not yet circulating.
Potential future sell pressure from unlocks.
```

### 🟡 Smart Money Positioning
```
Score contribution: +6

Top traders: 60% long
Retail:      43% long
Divergence:  +17%

Smart money is more bullish than retail.
Could indicate informed positioning — or distribution into retail.
Context dependent.
```

---

## Temporal Tracking — 4 Scans over 17.3h

```
Score: 50 → 50 → 50 → 50
Trend: ➡️ stable

Chronic signals (present in all 4 scans):
  GITHUB_ABANDONED
  THIN_BOOK_HIGH_OI
  SUPPLY_MODERATE_CIRC
  SMART_MONEY_LONG

Persistence: 100%

OI Δ scan-to-scan:    0.0%
Price Δ scan-to-scan: 0.0%
Funding Δ:            0.000000
Longs Δ:              0.0%

Regime: 🔀 MIXED
```

---

## Interpretation

```
What BORIS sees:

1. Squeeze setup is structural and persistent.
   26x OI/Depth ratio has been present across all 4 scans.
   It does not resolve on its own — it requires a liquidation event.

2. Development is dead.
   Price performance (+32.8% in 30d) has no development backing.
   Either market is pricing future expectations, or it's driven by
   other factors (narrative, CEX listing, coordinated buying).

3. Smart money is long.
   Top traders positioned 17% more bullish than retail.
   This is either accumulation before a move, or distribution.
   Cannot determine which without longer temporal window.

4. Organic probability: 41%.
   Majority of price action has non-organic characteristics.
```

---

## What BORIS Does Not Conclude

```
✗ Does not say "this will pump"
✗ Does not say "this will dump"
✗ Does not call this a scam
✗ Does not recommend buy or sell

BORIS identified:
  - A squeeze setup (structural, persistent)
  - An abandoned development signal
  - Smart money divergence from retail

What happens next depends on factors outside BORIS scope:
  market sentiment, macro, team actions, unlock schedules.
```

---

*BORIS beta 1.3 — Market Detection Engine*
*Sources: CoinGecko · Binance Futures · Bybit Futures · Binance Orderbook*
*Not investment advice.*
