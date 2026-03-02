# BORIS — System Architecture

## Overview

BORIS is a multi-layer intelligence system.
Each layer produces signals. Signals feed into correlation.
Correlation produces findings. Findings produce exploit chains.

No layer works in isolation.
The signal is in the intersection.

---

## Layer Stack
┌─────────────────────────────────────────────────────────┐
│                 INPUT                                    │
│   GitHub repo · Contract address · Token ticker         │
│   Explorer URL · owner/repo                             │
└────────────────────────┬────────────────────────────────┘
│
┌──────────────▼──────────────┐
│      ARCHETYPE ENGINE       │
│  Classifies protocol type   │
│  DEX · Stablecoin · DAO     │
│  Lending · Bridge · etc     │
│  Normalizes false positives │
└──────────────┬──────────────┘
│
┌────────────────────┼────────────────────┐
│                    │                    │
▼                    ▼                    ▼
┌────────┐         ┌──────────┐         ┌─────────┐
│ STATIC │         │ ONCHAIN  │         │ MARKET  │
│  CODE  │         │ STRUCT   │         │ +DERIVS │
└────┬───┘         └────┬─────┘         └────┬────┘
│                    │                    │
▼                    ▼                    ▼
┌────────┐         ┌──────────┐         ┌─────────┐
│EXPLOIT │         │  TRUST   │         │ SOCIAL  │
│ CHAINS │         │  MODEL   │         │  INTEL  │
└────┬───┘         └────┬─────┘         └────┬────┘
│                  │                    │
└──────────────────┼────────────────────┘
│
┌─────────────▼─────────────┐
│   CROSS-LAYER CORRELATION  │
│                           │
│  Code ↔ Onchain           │
│  Holder ↔ Governance      │
│  Liquidity ↔ Oracle       │
│  Behavior ↔ Structure     │
│  Social ↔ Code            │
└─────────────┬─────────────┘
│
┌─────────────▼─────────────┐
│      TEMPORAL ENGINE      │
│  Tracks changes over time │
│  Role Δ · Upgrade Δ       │
│  Holder Drift · OI Δ      │
│  Audit Drift              │
└─────────────┬─────────────┘
│
┌─────────────▼─────────────┐
│          OUTPUT           │
│  Structured report        │
│  Tier-filtered            │
│  JSON export              │
└───────────────────────────┘



---

## Modules

### 1. Static Code Analysis
- **Input:** GitHub repository (Solidity, Rust, Move, Go, Python, Java, C++, TypeScript, TON, Elixir, Shell)
- **Engines:** Slither · Mythril · Aderyn · Semgrep + custom detectors
- **Output:** Findings with file:line, severity, pattern classification
- **Key logic:** Archetype normalization before surfacing — DEX LP mint is not a backdoor

### 2. Onchain Structural Analysis
- **Input:** Contract address or GitHub repo (address extraction)
- **Chains:** ETH · BSC · Polygon · Arbitrum · Base · Optimism · Solana · Tron · Stellar
- **Output:** Proxy resolution, role map, admin surface, deployment graph
- **Key logic:** Follows proxy chains to implementation, extracts all privileged functions

### 3. Exploit Chain Modeling (Invariant Correlation Engine)
- **Input:** All findings from static + onchain layers
- **Output:** Multi-step exploit chains with prerequisites, scores, file binding
- **Key logic:** Connects isolated findings by prerequisite dependency graph

### 4. Market Layer
- **Input:** Token ticker or address
- **Sources:** DexScreener · CoinGecko · Binance · Bybit · OKX
- **Output:** Liquidity depth, OI analysis, derivatives positioning, manipulation signals
- **Key logic:** OI/Depth ratio, funding divergence, squeeze setup detection

### 5. Holder Model
- **Input:** Token contract address
- **Output:** Distribution index, whale map, CEX/LP correction, governance concentration
- **Key logic:** Real concentration = nominal minus CEX minus LP minus burn

### 6. Social Intelligence
- **Input:** Project name, GitHub repo, or direct links
- **Sources:** Telegram · X/Twitter · Discord
- **Output:** Engagement quality, impersonator detection, cross-platform consistency
- **Key logic:** View ratio analysis, Levenshtein impersonation matching

### 7. Funds Flow Analyzer
- **Input:** Contract or LP pool address
- **Output:** Wash trading signals, bot patterns, extraction detection
- **Key logic:** Graph-based cyclic flow detection, actor dominance scoring

### 8. Audit Drift Analysis
- **Input:** GitHub repo + PDF audit reports
- **Output:** Delta between audit state and current code, severity drift, new surfaces
- **Key logic:** Pattern overlap matching, git diff from audit commit

### 9. Attack Simulation Correlation
- **Input:** Repository (attacker mock detection)
- **Output:** Alignment index between simulation prerequisites and actual findings
- **Key logic:** Partial alignment = undeclared risk surface

### 10. Soroban Intelligence Module (SIM)
- **Input:** Stellar asset code or Soroban contract
- **Output:** Oracle manipulation surface, scam detection, market microstructure
- **Key logic:** VWAP oracle cost-to-manipulate calculation, factory impersonation detection

---

## Continuous Radar
GitHub Radar          → Monitors new repositories in real-time
Scores across 20+ signals
Auto-triggers scanner on top findings

DeFiLlama Radar       → New protocols from DeFiLlama feed
TVL filter + category + GitHub discovery

Verified Contract     → New verified contracts on EVM chains
Radar                   RPC + Etherscan V2 API
ETH · BSC · Polygon · Arbitrum · Base · Optimism

Stellar/Soroban       → New assets via Horizon API
Radar                   SDEX monitoring · scam factory detection



---

## Data Flow Example
Input: github.com/protocol/contracts

Archetype Engine
→ Detected: DAO_GOVERNANCE (90% confidence)
→ Normalization: blacklist/pause flagged as contradictions, not by-design

Static Analysis
→ 269 findings raw
→ 36 normalized by archetype
→ Net: 233 surfaced

Onchain
→ 31 contracts found across ETH/BSC/ARB/POLYGON
→ 3 proxy chains resolved
→ Governance: NO_SNAPSHOT confirmed onchain

Exploit Chain Engine
→ Chain #1: flash_loan_governance (Score: 67)
Prerequisites: NO_SNAPSHOT + ARBITRARY_CALL
Both confirmed in static + onchain layers

Market
→ Liquidity: $659K across 2 pools
→ Pool manipulation: 85/100 (wash trading confirmed)
→ Flash loan borrowing: feasible at current DEX depth

Holders
→ Top-10 real: 88.3%
→ #1 holder (59.45%) = governance contract
→ Flash loan threshold: ~20% needed, achievable at $659K liquidity

Cross-Layer Correlation
→ NO_SNAPSHOT + thin liquidity + concentrated holders
→ Signal: FLASH_LOAN_GOVERNANCE_FEASIBLE
→ Amplifier score: HIGH

Audit Drift
→ Last audit: 549 days ago
→ 48 new findings outside audit scope
→ Signal: STALE_AUDIT_CRITICAL_DRIFT

Output
→ BLACKBOX report: 4 exploit chains
→ Highest chain score: 67/100
→ Verdict: HIGH RISK — EXPLOITABLE_GOVERNANCE



---

## Design Principles
No fabrication
Every signal references a specific file, address, or data point.
BORIS does not infer from vibes.

Archetype-first normalization
A finding is only a risk if it’s a risk in context.
LP mint in a DEX is not a backdoor.
LP mint in a “fully decentralized savings protocol” is.

Correlation over isolation
Single findings are weak signal.
Correlated findings across layers are strong signal.

Temporal awareness
Current state is not final state.
BORIS tracks drift — what changed, when, how much.

Explicit uncertainty
Every exploit chain has a confidence score.
BORIS does not claim certainty it doesn’t have.
