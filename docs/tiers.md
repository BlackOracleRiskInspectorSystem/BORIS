# BORIS — Tier Breakdown

Detailed description of what each tier produces and why.

---

## Philosophy

BORIS does not have a "free trial" that teases paid features.
Each tier is a different **type** of intelligence, not just more of the same.
GUEST    → Surface map. You see the shape of risk.
RADAR    → Pressure map. You understand the risk structure.
RAW      → Data map. No interpretation. Pure technical facts.
BLACKBOX → Consequence map. Exploit paths. Full stack.



---

## 👁️ GUEST — Free

**Who it's for:** First look. Due diligence starting point.

**What you get:**
- Summary with overall risk classification
- Risk level (CRITICAL / HIGH / ELEVATED / MODERATE)
- Archetype detection
- Whether the project is deployed
- Whether audits exist

**What you don't get:**
- Any finding details
- File names or line numbers
- Exploit paths
- Holder/liquidity/social data
- Addresses

**Limits:** 3 scans/day · 1 parallel

**Example output:**
🔴 HIGH RISK
Archetype: DAO / Governance
Deployed: YES
Audits: YES (last: 549 days ago — STALE)
Critical findings present.
[Details available in RADAR tier and above]



---

## 🟥 RADAR — $19/mo

**Who it's for:** Investors, fund managers, protocol evaluators doing regular screening.

**What you get:**
- Everything in GUEST
- Risk categories with severity counts (C/H/M/L — numbers only, no details)
- Governance analysis: claimed vs observed model
- Admin control score
- Behavioral score (aggregated)
- Audit context: existence, age, coverage level
- Discovery feed access
- Continuous Radar 24/7
- DeFiLlama scanner 24/7
- Batched alerts (every 12–24h)
- JSON export (summary)

**What you don't get:**
- Specific file names or line numbers
- Exploit chain details
- Social intelligence details
- Funds flow analysis

**Limits:** 25 scans/day · 1 parallel

**Example output:**
🔴 HIGH RISK — Score: 82/100
Governance: CLAIMED=DAO | OBSERVED=centralized (mismatch)
Admin control: 100/100
Findings: C:5 H:45 M:60 L:58
Audit: 6 audits | last 549d ago ⚠️ STALE
Behavioral: CRITICAL (manipulation detected)
[File-level details available in RAW tier]



---

## 📋 RAW — $29/mo

**Who it's for:** Security researchers, developers, auditors who read code.

**What you get:**
- Everything in RADAR
- Full finding list with file:line for every finding
- Archetype + governance model detail
- Complete holder distribution with CEX/LP correction
- Liquidity analysis per pool
- Deployment graph (all contracts, chains, proxy resolution)
- CEX listings
- ABI surface analysis
- JSON export (full technical data)

**What you don't get:**
- Exploit chains (paths connecting findings)
- Social intelligence
- Funds flow analysis
- Code fragments

**Philosophy:** No scores on individual findings. No verdicts. No "this is dangerous."
Just: here is the data, here is the location, you decide what it means.

**Limits:** 30 scans/day · 1 parallel

**Example output:**
NO_SNAPSHOT
File: contracts/gov/GovPool.sol
Line: 218
Pattern: flash_loan_governance

ARBITRARY_CALL

File: contracts/gov/proposals/DistributionProposal.sol
Line: 65

CENTRALIZED_CONTROL ×25
contracts/gov/validators/GovValidators.sol:111
contracts/gov/ERC721/multipliers/ERC721Multiplier.sol:18
… +23 more

Holders (BSC):
Total: 47,212
Top-10: 93.4% | Real: 88.3%
#1: 0xbe8cb1… 59.45% (contract)
…



---

## 🔥 BLACKBOX — $49/mo

**Who it's for:** Security professionals, protocol teams pre-launch, funds with significant exposure.

**What you get:**
- Everything in RAW
- Exploit paths: full multi-step chains with prerequisites, scores, confidence
- Audit drift: full analysis (what changed since last audit, severity shift, new surfaces)
- Deploy trace analysis
- Code fragments at finding locations
- Social intelligence (full report)
- Funds Flow Intelligence
- Address Profiler
- Attack Simulation Correlation (mock/PoC alignment)
- Instant real-time alerts
- Priority processing 24/7
- First access to all beta features
- JSON export (full)

**Limits:** Unlimited scans · 2 parallel + queue 5

**Example output:**
Chain #1: Flash-loan governance capture
Score: 67 | Confidence: 75%
Prerequisites: NO_SNAPSHOT + ARBITRARY_CALL
Steps:
1. Flash-loan governance token on DEX
2. Call vote() — no snapshot, power = current balance
3. Pass proposal with arbitrary external call
4. Execute drain/mint via passed proposal
5. Repay flash loan same tx
Code:
// GovPool.sol:218
function vote(uint256 proposalId, bool isVoteFor, uint256 voteAmount …
// No snapshot. Attack cost: flash loan fee only.
Patch: Add ERC20Snapshot or block-based checkpoint.



---

## Comparison

|  | 👁️ GUEST | 🟥 RADAR | 📋 RAW | 🔥 BLACKBOX |
|--|:--:|:--:|:--:|:--:|
| **Price** | Free | $19/mo | $29/mo | $49/mo |
| **Scans/day** | 3 | 25 | 30 | Unlimited |
| **Parallel** | 1 | 1 | 1 | 2 + queue 5 |
| Risk classification | ✓ | ✓ | ✓ | ✓ |
| Severity counts | — | ✓ | ✓ | ✓ |
| Governance model | — | ✓ | ✓ | ✓ |
| Admin control score | — | ✓ | ✓ | ✓ |
| Audit context | — | ✓ | ✓ | ✓ |
| File:line findings | — | — | ✓ | ✓ |
| Holder distribution | — | — | ✓ | ✓ |
| Deployment graph | — | — | ✓ | ✓ |
| Liquidity analysis | — | — | ✓ | ✓ |
| Exploit chains | — | — | — | ✓ |
| Code fragments | — | — | — | ✓ |
| Audit drift (full) | — | — | — | ✓ |
| Social intelligence | — | — | — | ✓ |
| Funds Flow | — | — | — | ✓ |
| Attack sim correlation | — | — | — | ✓ |
| Continuous Radar | — | ✓ | ✓ | ✓ |
| Alerts | — | Batched | Batched | Instant |
| JSON export | — | Summary | Full tech | Full |
| Beta access | — | — | — | First |
