# BORIS — Token Holders Analysis
**Target:** EVM Token — *address redacted*
**Chain:** BSC
**Engine:** BORIS beta 1.3 — Holders Analyzer
**Supports:** EVM (ETH · BSC · ARB · BASE · OP · POLY) · Solana · Tron

---

## Summary

```
Total Holders  : 47,212
Centralization : 🔴 CRITICAL (75/100)

Top-10 hold    : 93.4%
Top-20 hold    : 98.9%
Top-10 (real)  : 88.3%  ← after burn / pool / CEX exclusion

In Pools       : 0.0%
On CEX         : 8.0%
Whales (>2%)   : 85.6%
```

---

## Top Holders

```
Rank  Type      Address              Share    Value
────────────────────────────────────────────────────
  1.  📄 contract  0xbe8cb1...71b7b2  59.45%  $48.0M
  2.  🏦 CEX       0xf97781...41acec   5.84%   $4.7M  Binance Hot Wallet 20
  3.  📄 contract  0xb56212...7c0f0b   5.53%   $4.5M
  4.  📄 contract  0x99e830...e766a8   4.15%   $3.4M
  5.  📄 contract  0xcbe043...850133   3.84%   $3.1M
  6.  📄 contract  0x708917...c51c7c   3.54%   $2.9M
  7.  📄 contract  0xe95d26...b50146   3.52%   $2.8M
  8.  📄 contract  0x30639c...9dc907   3.39%   $2.7M
  9.  📄 contract  0x96de85...0b9f8e   2.21%   $1.8M
 10.  📄 contract  0xd9f839...fe8953   1.92%   $1.6M
 ──────────────────────────────────────────────────
 11.  🏦 CEX       0x5a52e9...70efcb   1.17%    $946K  Binance 28
 12.  👤 wallet    0x820b1a...45b102   0.75%    $602K
 13.  👤 wallet    0x5ce86d...f58eb5   0.65%    $522K
 14.  📄 contract  0x1b0f59...aa845b   0.56%    $454K
 15.  🏦 CEX       0x53f78a...f3fa23   0.56%    $450K  KuCoin Hot Wallet 2
 16.  👤 wallet    0xde8d7b...93f262   0.48%    $390K
 17.  👤 wallet    0x0c2006...94d545   0.42%    $340K
 18.  🏦 CEX       0x124d9b...44f012   0.37%    $301K  LBank Hot Wallet 5
 19.  📄 contract  0x23ab35...415f2a   0.27%    $215K  ← LP pool (BSC)
 20.  👤 wallet    0x6abe21...29cb9f   0.25%    $206K
      ... +47,192 more
```

---

## Concentration Analysis

```
Nominal Top-10:  93.4%

Real Top-10 breakdown:
  Contract holders:  ~85.6%  (governance contracts, vesting, treasury)
  CEX wallets:        ~8.0%  (Binance, KuCoin, LBank — excluded from real)
  Real Top-10:       88.3%   ← what matters for governance/rug analysis

Single dominant holder: #1 at 59.45% ($48M)
  Type: contract — not a simple wallet
  Implication: governance effectively controlled by this contract's logic
```

---

## Signal Interpretation

```
🔴 CRITICAL centralization

What 59.45% in one contract means:
  → Whoever controls that contract controls token governance
  → Any proposal requiring majority vote is pre-decided
  → Emergency functions executable without community consensus
  → Flash-loan governance attack amplified (lower threshold needed)

What 93.4% Top-10 means:
  → 47,202 holders share 6.6% of supply
  → Retail holders are price passengers, not participants
  → Liquidity exit by top holders = price collapse for retail

CEX normalization:
  → Raw Top-10: 93.4%
  → After removing Binance/KuCoin/LBank: 88.3%
  → CEX holdings represent float — not governance power
  → Real concentration is governance-relevant figure
```

---

## Cross-Layer Implication

```
Combined with code findings:

Holder #1 (59.45%) controls contract
+ NO_SNAPSHOT in governance voting
+ ARBITRARY_CALL in governance proposals

= Flash-loan governance attack threshold is low.
  Attacker needs to temporarily acquire ~20-25% to pass proposals
  if top holder is neutral. At current liquidity ($659K DEX),
  this is within reach of a well-funded attacker.

Holder concentration amplifies every governance vulnerability.
```

---

*BORIS beta 1.3 — Holders Analyzer*
*Supported: EVM (ETH · BSC · ARB · BASE · OP · POLY) · Solana · Tron*
