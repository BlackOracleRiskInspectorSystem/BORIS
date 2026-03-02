# BORIS — Full BLACKBOX Report
**Target:** Governance Protocol (DAO) — *name redacted*
**Scan date:** 2026-03-02
**Engine:** BORIS beta 1.3
**Tier:** BLACKBOX

---

## Summary

```
Status:   🚨 HIGH RISK
Class:    EXPLOITABLE_GOVERNANCE + PRICE_MANIPULATION + RUG_PULL_PATTERN
Deployed: YES (31 contracts — ETH · BSC · ARB · POLYGON)
Funds at risk: YES
Exploit paths: PRESENT (4 chains)
```

---

## Archetype

```
Detected:  DAO / Governance Protocol (confidence: 90%)
Claimed:   DAO — decentralized governance
Observed:  Restricted role cluster with broad execution authority

⚠️  Narrative mismatch detected
    Code contains: blacklist · pause · emergency_withdraw
    Claim: fully decentralized
```

> A `pause()` in a stablecoin is by design.
> A `pause()` in a "fully decentralized DAO" is a red flag.
> BORIS normalizes by archetype. This one didn't normalize out.

---

## Vulnerability Summary

```
Total:     269 findings
🔴 Critical:  5
🟠 High:     45
🟡 Medium:   60
⚪ Low:      58

36 patterns normalized by archetype (DAO_GOVERNANCE — not surfaced)
```

---

## Critical Findings

### 🔴 NO_SNAPSHOT ×3 — Flash-loan governance attack surface

```
GovPool.sol:218
GovValidators.sol:117
GovPoolVote.sol:29

Impact: Voting power = current token balance.
        No historical checkpoint.
        Flash-loan $X of governance token → vote → repay.
        Cost: flash loan fee only.
```

```solidity
// GovPool.sol:218
function vote(
    uint256 proposalId,
    bool isVoteFor,
    uint256 voteAmount,
    ...
// No snapshot. No block-based checkpoint.
// Balance at vote time = attack surface.
```

### 🔴 ARBITRARY_CALL ×2

```
DistributionProposal.sol:65
GovUserKeeper.sol:795

Impact: Governance proposal can execute arbitrary external calls.
        Combined with NO_SNAPSHOT = governance capture → arbitrary execution.
```

---

## High Findings (selected)

```
CENTRALIZED_CONTROL     ×25   GovValidators.sol · ERC721Multiplier.sol · +9 files
HIDDEN_MINT_FUNCTION    ×11   TokenSaleProposal.sol · GovValidatorsToken.sol · +8 files
OFFCHAIN_SIGNATURE_RISK  ×3   GovPoolOffchain.sol · TokenSaleProposalRecover.sol
AMM_SPOT_ORACLE          ×2   GovUserKeeper.sol · NetworkProperties.sol
EMERGENCY_DRAIN          ×1   TokenSaleProposal.sol:18
TX_ORIGIN_AUTH           ×1   PoolFactory.sol:315
ACCESS_CONTROL_MISCONFIG ×1   PoolRegistry.sol (76 files affected)
```

---

## Exploit Chains

### Chain #1 — Flash-loan Governance Capture
```
Score: 67 | Confidence: 75% | Vector: flash_loan_governance

Step 1: Flash-loan governance token on liquid DEX (Uniswap/Balancer/Aave)
Step 2: Call vote() — no snapshot, power = current balance
Step 3: Pass proposal with arbitrary external call
Step 4: Execute drain / mint via passed proposal
Step 5: Repay flash loan same tx

Prerequisites: ARBITRARY_CALL + NO_SNAPSHOT
Amplifiers:    SOCIAL_WEAK · FLOW_MANIPULATION · HOLDERS_CONCENTRATED · STALE_AUDIT

Files: NetworkProperties.sol · ERC20Gov.sol · ERC20GovCapped.sol

Patch: Add ERC20Snapshot or block-based checkpoint.
       Require proposal delay + minimum holding period before vote counts.
```

### Chain #2 — Oracle Manipulation via Spot Price
```
Score: 48 | Confidence: 80% | Vector: price_manipulation

Step 1: Flash loan base asset
Step 2: Swap on AMM → move spot price (oracle reads spot)
Step 3: Borrow/mint against inflated collateral
Step 4: Swap back, repay flash loan

Prerequisites: AMM_SPOT_ORACLE
Files: NetworkProperties.sol · GovUserKeeper.sol · UniswapPathFinder.sol

Patch: Use Chainlink / TWAP. Add price deviation circuit breaker.
```

### Chain #3 — Cross-file Escalation: Governance → Treasury
```
Score: 42 | Confidence: 70% | Vector: flash_loan_governance

Step 1: Exploit governance (GovValidators.sol · DistributionProposal.sol)
Step 2: Pass proposal with arbitrary call targeting treasury
Step 3: Treasury has ACCESS_CONTROL_MISCONFIG
Step 4: Execute drain via governance proposal

Patch: Separate governance timelock from treasury access.
       Independent multisig + timelock on treasury.
```

### Chain #4 — Privileged Control Concentration
```
Score: 26 | Confidence: 82% | Vector: rug_pull

Evidence:
  + Social presence weak
  + Token holders highly concentrated (Top-10: 93.4%)
  + High admin control score
  + On-chain flow manipulation detected
  + Emergency drain function present
  + Hidden/unbounded mint capability

Anti-signals:
  - 6 audits by 4 firms
  - 31 deployed contracts

Note: Behavioral/contextual — not a code vulnerability.
      Pattern matches known rug pull indicators.
```

---

## Attack Simulation Correlation

```
Simulations found in repo: 4 attacker mock contracts
Alignment density: 46.2% (6/13 prerequisites matched)
```

```
GovPoolAttackerMock.sol
  Declared:  ARBITRARY_CALL · FLASH_LOAN_GOVERNANCE · GOVERNANCE_MANIPULATION · NO_SNAPSHOT
  Observed:  ARBITRARY_CALL · NO_SNAPSHOT
  Match:     2/4 🔸 partial_alignment

GovPoolAttackerSlaveMock.sol
  Declared:  ARBITRARY_CALL · GOVERNANCE_MANIPULATION · NO_SNAPSHOT
  Observed:  ARBITRARY_CALL · NO_SNAPSHOT
  Match:     2/3 🔸 partial_alignment

ERC721MultiplierAttackerMock.sol
  Declared:  REENTRANCY · SAME_TX_MANIPULATION
  Observed:  none
  Match:     0/2 ⬜ prerequisites_not_observed

Findings without any simulation artifact:
  ACCESS_CONTROL_MISCONFIG · AMM_SPOT_ORACLE · CENTRALIZED_CONTROL
  EMERGENCY_DRAIN · HIDDEN_MINT_FUNCTION · OFFCHAIN_SIGNATURE_RISK · TX_ORIGIN_AUTH
```

---

## Audit Drift

```
Audits:    6 total (Ambisafe ×3 · CertiK · Cyfrin · Hacken)
Last:      2024-08-30 — 549 days ago ⚠️ STALE
Drift:     🔴 CRITICAL (70/100)

Severity shift:
  Critical: 3 → 5  (+2)
  High:     2 → 47 (+45)

Audit findings:
  Still present:     4
  Potentially fixed: 10
  New (not in scope): 48

New issues outside audit scope:
  CENTRALIZED_CONTROL    ×24
  HIDDEN_MINT_FUNCTION   ×11
  NO_SNAPSHOT            ×3
  + 5 more types

Unaudited files with critical/high issues:
  contracts/gov/ERC20/ERC20Gov.sol        (1 issue)
  contracts/gov/ERC20/ERC20GovCapped.sol  (2 issues)
```

---

## Deployment Graph

```
Total contracts: 31
Chains: ETH (14) · BSC (16) · POLYGON (1)

BSC — proxies:
  ERC1967Proxy          ×3   (implementation: unknown)
  ProtectedTransparentProxy ×5   (implementation: unknown)
  ProtectedPublicBeaconProxy ×1

ETH:
  Token contract — 5y old ✓
  ERC1967Proxy — 1y old → impl: BABTMockOwnableUpgradeable ✓
  Not verified: 9 contracts (2 with ETH balance)

Not verified but holding funds:
  0x4fBa1c... — 0.1341 ETH
  0xfff997... — 0.1195 ETH
```

---

## Liquidity & Funds Flow

```
Pools:        5 | Total liquidity: $659,084
CEX listings: 38 (Binance · HTX · MEXC · Pionex · WhiteBIT)
CEX Vol 24h:  $6,342,564
```

```
Pool ETH/WETH — $287,982
  Risk: 70/100 | Manipulation: 70/100
  ⚠️  WASH_TRADING: 0x278d858f... ↔ pool
  ⚠️  WASH_TRADING: 0x1dc89ab2... ↔ pool

Pool BSC/USDT — $340,071
  Risk: 85/100 | Manipulation: 85/100
  ⚠️  WASH_TRADING: 0x278d858f... — 56 swap events (85% confidence)
  ⚠️  WASH_TRADING: 0x4923d960... — 42 swap events
  ⚠️  WASH_TRADING: 0x2f0cabba... — 38 swap events
  Dominant actor: 0x278d858f — 18.7% of pool activity
```

---

## Holders

```
Chain:        BSC
Total:        47,215 holders
Centralization: 🔴 CRITICAL (75/100)

Top-10:       93.4%
Real Top-10:  88.3% (after CEX/LP correction)

#1  0xbe8cb1...71b7b2  59.5%  (contract)
#2  0xf97781...41acec   5.8%  (Binance Hot Wallet 20)
#3  0xb56212...7c0f0b   5.5%
#4  0x99e830...e766a8   4.2%
#5  0xcbe043...850133   3.8%
```

---

## Social Intelligence

```
Risk:  44/100
Trust: 48/100
Platforms analyzed: 16

Telegram: 15 channels (2 official) | 92,749 total subscribers
  @xxxxxxxx_network:              8,100  WEAK
  @xxxxxxxx_network_official_chat: 59,474  WEAK
  @xxxxxxxxNetworkSpanish:          159   DEAD
  @xxxxxxxxnetworkann:               83   DEAD
  + 11 more (dead/discovered)

X/Twitter: 315,842 followers | WEAK

🚨 IMPERSONATORS: 5 detected
  @xxxx_network_official_chats   → impersonates @xxxx_network_official_chat
  @xxxx_networkk                 → impersonates @Xxxx_network
  @xxxx_network_officiaI         → impersonates @Xxxx_network
  @xxxx_network_officialchat     → impersonates @xxxx_network_official_chat
  @xxxx_network_official_chatt   → impersonates @xxxx_network_official_chat

Cross-platform patterns:
  COMMUNITY_FRAGMENTED (70%) — 15 TG entities, fragmented presence
  BOT_INFLATED (75%)         — 3 dead channels with 5k–7k subscribers
```

---

## Structural Profile

```
🔴 Governance risk:       95/100
🔴 Holder concentration:  75/100
🔴 Liquidity risk:        70/100
🟡 Code pattern density:  46/100
🟡 Social trust:          48/100
🟠 Behavioral risk:      100/100
```

---

## Verdict

```
🚨 HIGH RISK

Class: EXPLOITABLE_GOVERNANCE + PRICE_MANIPULATION + RUG_PULL_PATTERN

❌ Not safe for public deployment / production capital
❌ Active exploit paths exist
⚠️  Patch critical issues before adding TVL

Immediate actions required:
  1. Add ERC20Snapshot or block-based voting checkpoint
  2. Replace AMM spot oracle with Chainlink / TWAP
  3. Separate treasury timelock from governance execution
  4. Audit new files outside previous audit scope (48 findings)
  5. Investigate unverified contracts holding ETH balance
```

---

*BORIS beta 1.3 | Scan: 2026-03-02 | Not investment advice.*
