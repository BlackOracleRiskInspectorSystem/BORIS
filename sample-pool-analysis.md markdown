# BORIS — Funds Flow Analysis
**Target:** Liquidity pools (EVM)
**Chains:** BSC · Ethereum
**Period:** 14 days
**Engine:** BORIS beta 1.3 — Funds Flow module

---

## Pools Analyzed

```
Pool A: DEX/WETH — Ethereum  ($287,982 liquidity)
Pool B: DEX/USDT — BSC       ($340,071 liquidity)
```

---

## Pool A — Ethereum

```
Risk:         70/100
Manipulation: 70/100
Bot Activity:  0/100

Token transfers analyzed: 1,000
Addresses profiled:       53
  wallet=49 · contract=2 · dex=2

Signals:
  ⚠️  WASH_TRADING: 0x278d858f... ↔ pool (recurring)
  ⚠️  WASH_TRADING: 0x1dc89ab2... ↔ pool (recurring)
```

---

## Pool B — BSC

```
Risk:         85/100
Manipulation: 85/100
Bot Activity:  0/100

Token transfers analyzed: 300
Addresses profiled:       15 (all wallet)
```

### Wash Trading Signals

```
🚨 0x278d858f...  56 swap events  Confidence: 85%
🚨 0x4923d960...  42 swap events  Confidence: 85%
🚨 0x2f0cabba...  38 swap events  Confidence: 85%
🚨 0x73b4c818...  32 swap events  Confidence: 85%
🔴 0x8c8b5293...  28 swap events  Confidence: 85%
🔴 0xf55b3aa3...  18 swap events  Confidence: 85%
🔴 0x031942f2...  16 swap events  Confidence: 85%
```

### Flow Statistics

```
Incoming transfers: 150  |  Value IN:  6,087.59 tokens
Outgoing transfers: 150  |  Value OUT: 5,895.90 tokens
Net:                  0  |  Net:        +191.69 tokens

Top Senders (= Top Receivers — circular flow):
  0x278d85...  1,276 IN → 1,347 OUT
  0xf55b3a...  1,158 IN → 1,199 OUT
  0x2f0cab...    911 IN →   900 OUT
  0x8c8b52...    676 IN →   721 OUT
  0xd060a0...    518 IN →   518 OUT
```

### Key Actors

```
0x278d858f...  28 swaps  18.7% of pool activity  ← dominant
0x4923d960...  21 swaps
0x2f0cabba...  19 swaps
0x73b4c818...  16 swaps
0x8c8b5293...  14 swaps
```

---

## Interpretation

```
Pattern: Same addresses appear as both top senders and receivers.
         Inflow ≈ Outflow per address.
         High swap count, low net value transfer.

Classification: Wash trading
                Volume inflation
                Organic activity: ~15% estimated

Signal: Reported 24h volume does NOT reflect organic trading.
        Liquidity appears deeper than it is functionally.
        Pool volume numbers are not reliable for market assessment.
```

---

## Signal Summary

```
Total signals: 19

🚨 Critical: 4  (WASH_TRADING — high frequency)
🔴 High:     3  (WASH_TRADING — medium frequency)
🟠 Medium:   7  (WASH_TRADING + BOT_PATTERN)
🟡 Low:      1  (WHALE_ACCUMULATION)

Wash Trading:   13 signals
Bot Activity:    4 signals
Whale Activity:  1 signal
Organic:         1 signal
```

---

*BORIS beta 1.3 — Funds Flow module*
*Supported chains: EVM · Solana · Tron*
