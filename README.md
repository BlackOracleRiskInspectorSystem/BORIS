<div align="center">

<img src="boris_logo.png" alt="BORIS" width="320"/>

# BORIS Beta v 1.3
### Black Oracle Risk Inspection System

**Threat surface intelligence for Web3 protocols.**

*Code doesn't lie. Narratives do.*

[![Bot](https://img.shields.io/badge/Telegram-Bot-2CA5E0?style=flat&logo=telegram)](https://t.me/BlackOracleBORIS_bot)
[![EN](https://img.shields.io/badge/Channel-EN-2CA5E0?style=flat&logo=telegram)](https://t.me/Black_Oracle_BORIS_eng)
[![RU](https://img.shields.io/badge/Channel-RU-2CA5E0?style=flat&logo=telegram)](https://t.me/Black_Oracle_BORIS_ru)
[![Twitter](https://img.shields.io/badge/Twitter-@BlackOracleRoot-000000?style=flat&logo=x)](https://x.com/BlackOracleRoot)

![Status](https://img.shields.io/badge/status-live-brightgreen)
![Files](https://img.shields.io/badge/codebase-60%20files%20%7C%2078k%20lines-blue)
![Functions](https://img.shields.io/badge/functions-1%2C169-blue)
![Languages](https://img.shields.io/badge/languages-10%2B-orange)
![Chains](https://img.shields.io/badge/chains-EVM%20%7C%20Solana%20%7C%20Tron%20%7C%20Stellar-orange)

</div>

---

## What BORIS is not
✗  Not a “rug checker”
✗  Not a safety score
✗  Not investment advice
✗  Not “scam / not scam”
✗  Does not care about brand, reputation, or market cap



## What BORIS is

BORIS maps **where control lives** and **how capital can move**.

When code claims decentralization but contains `pause()` + `blacklist()` + `emergencyWithdraw()` — BORIS shows the gap.  
When an audit is 549 days old and 48 new execution surfaces appeared since — BORIS shows the drift.  
When governance has no snapshot mechanism and liquidity exists for flash-loan borrowing — BORIS builds the chain.

Every layer feeds every other layer.  
That's where the real signal is.

---

## Architecture

<table>
<tr>
<td colspan="6" align="center">

**CROSS-LAYER CORRELATION ENGINE**  
`Code ↔ Onchain ↔ Holders ↔ Market ↔ Social ↔ Derivatives`

</td>
</tr>
<tr>
<td align="center">📦<br/><b>STATIC</b><br/><sub>10+ languages<br/>4 engines</sub></td>
<td align="center">🔎<br/><b>ONCHAIN</b><br/><sub>Proxy · ABI<br/>Trust Model</sub></td>
<td align="center">⚠️<br/><b>MARKET</b><br/><sub>Spot · OI<br/>Derivatives</sub></td>
<td align="center">🛰<br/><b>SOCIAL</b><br/><sub>TG · X<br/>Discord</sub></td>
<td align="center">🔐<br/><b>GOVERNANCE</b><br/><sub>Privilege<br/>Drift</sub></td>
<td align="center">📡<br/><b>RADAR</b><br/><sub>24/7<br/>Live</sub></td>
</tr>
<tr>
<td colspan="6" align="center">

**TEMPORAL ENGINE** — `Role Δ · Upgrade Δ · Holder Drift · OI Δ · Audit Drift`

</td>
</tr>
</table>

---

## Capability Matrix

<details>
<summary><b>📦 1. Static Code Analysis — 10+ languages, 4 engines</b></summary>

**Languages:**  
`Solidity` · `Rust` · `Move (Aptos/Sui)` · `Go` · `Python` · `Java` · `C++` · `TypeScript` · `TON (FunC/Tact/Fift)` · `Elixir` · `Shell`

**Engines:** Slither · Mythril · Aderyn · Semgrep + custom detectors

| Pattern | Severity |
|---------|----------|
| Reentrancy (standard + read-only) | CRITICAL |
| Delegatecall misuse | CRITICAL |
| Arbitrary call surface | CRITICAL |
| Emergency drain patterns | CRITICAL |
| Hidden backdoor signatures | CRITICAL |
| Unchecked transfer / return | HIGH |
| Oracle spot-price dependency | HIGH |
| Mint / burn without bounds | HIGH |
| Proxy upgrade surface | HIGH |
| Storage layout collision | HIGH |
| Flash-loan governance vectors | MEDIUM |
| Privileged role escalation | MEDIUM |

- Precise `file:line` mapping for every finding
- Custom risk taxonomy
- Pattern classification: CRITICAL / HIGH / MEDIUM / LOW / INFO

</details>

<details>
<summary><b>🔎 2. Onchain Structural Analysis</b></summary>

**Chains:** Ethereum · BSC · Polygon · Arbitrum · Base · Optimism · Solana · Tron · Stellar/Soroban

**Proxy Resolution:**
- ERC1967, UUPS, Transparent Proxy, custom patterns
- Implementation discovery
- Upgrade surface detection
- Storage layout inspection + collision detection

**Role & Control Mapping:**
- Privileged role extraction
- Role distribution mapping
- Admin function surface mapping: `pause` / `blacklist` / `emergencyWithdraw` / `upgradeTo`
- Deployment surface mapping
- Multi-contract linkage: factory → router → vault → token

</details>

<details>
<summary><b>🧠 3. Archetype Normalization — false positive reduction</b></summary>

Reduces false positives through architectural context.

- Stablecoin normalization — `blacklist` / `mint` / `freeze` flagged as by design
- DEX normalization — LP mint/burn, spot oracle patterns flagged as by design
- Liquidity staking normalization
- Governance protocol normalization
- LP pair normalization
- Router normalization
- Factory-driven architecture context

> Findings are scored against protocol archetype before surfacing.  
> A `blacklist()` in a stablecoin is not a backdoor. In a gaming token, it is.

</details>

<details>
<summary><b>🔗 4. Exploit Chain Modeling — Invariant Correlation Engine</b></summary>

Isolated findings become real attack paths.

- Prerequisite-based scenario modeling
- Multi-step exploit chain modeling
- Flash-loan scenario simulation (logical)
- Governance capture chains
- Oracle manipulation chains
- Storage corruption chains
- Conditional impact mapping
- Likelihood / impact heuristic scoring
- Context amplifiers: liquidity depth · holder concentration · role density

| Chain | Key Prerequisites |
|-------|------------------|
| Flash-loan governance capture | `NO_SNAPSHOT` + `ARBITRARY_CALL` + liquid market |
| Proxy hijack via delegatecall | `DELEGATECALL` to user-controlled address |
| Admin rug: drain + upgrade | Owner key + no timelock + `EMERGENCY_DRAIN` |
| Oracle manipulation → cascade | Spot oracle on thin DEX pool |
| Storage corruption via collision | Overlapping proxy storage slots |
| Cross-file privilege escalation | Role granted in initializer across files |
| Infinite approval drain | `approve(addr, MAX)` + no spend validation |

</details>

<details>
<summary><b>📊 5. Market Layer — Spot & Liquidity</b></summary>

- DEX pool aggregation (DexScreener)
- Liquidity depth analysis
- Volume / liquidity ratio
- CEX presence detection (CoinGecko)
- Pool fragmentation analysis
- Cyclic transaction sequence detection
- Flow manipulation heuristics
- Organic activity estimation
- Peak index detection

</details>

<details>
<summary><b>🐋 6. Holder Model</b></summary>

- Holder distribution index
- Top-10 concentration
- Real concentration correction — pools / CEX normalization
- Whale classification
- Contract holder classification
- Proxy holder detection
- LP concentration detection
- Extreme single holder detection
- Governance concentration heuristics

**Sources:** Etherscan · BscScan · Blockscout · Helius (Solana) · Rugcheck · Tronscan

**Example output:**  
`🔴 extreme (Top10 > 88%) — #1 holds 59.5% (contract) · #2 Binance Hot Wallet 5.8%`  
`Real concentration after CEX/LP correction: 88.3%`

</details>

<details>
<summary><b>🧬 7. Trust Model Extraction</b></summary>

Defines the actual trust assumptions of the system.

- Explicit trust assumption mapping
- Role-dependency mapping
- External assumption detection
- Governance override surface
- Emergency privilege exposure
- Trust failure consequence modeling

</details>

<details>
<summary><b>🧩 8. ABI Surface Intelligence</b></summary>

- ABI parsing
- Privileged function extraction
- Payable surface detection
- Fallback / receive detection
- State-changing vs view mapping
- Function density profiling
- Upgradeable surface exposure
- Cross-contract callable surface mapping

</details>

<details>
<summary><b>🛰 9. Behavioral Layer</b></summary>

- Cyclic swap detection
- Concentrated trader detection
- Flow clustering
- Suspicious repetition heuristics
- Temporal activity spikes
- Liquidity event correlation
- Trader dominance scoring

</details>

<details>
<summary><b>📉 10. Audit Drift Analysis</b></summary>

Audits are snapshots. BORIS tracks what changed after.

- Repo vs deployed bytecode divergence
- Pattern delta vs previous scans
- Severity drift tracking
- Prerequisite drift tracking
- Governance mutation detection
- Structural surface expansion detection
- Findings without simulation artifacts
- Simulation artifacts without findings
- Alignment density calculation
- Structural mismatch detection

**Supported audit firms:** OpenZeppelin · Trail of Bits · Sherlock · Code4rena · Cyfrin · Hacken · Ambisafe

**Example output:**
Audits: 6 | Last: 2024-08-30 (549d) ⚠️ STALE
Was: C3/H2 → Now: C5/H45
Still present: 4 | Potentially fixed: 10 | New (outside audit scope): 48
Files outside audit coverage: GovUserKeeper.sol · GovValidators.sol · GovPool.sol



</details>

<details>
<summary><b>🎭 11. Mock / Attack Simulation Correlation</b></summary>

BORIS detects attacker mock contracts in the repo and correlates them with real findings.

- Attacker mock detection
- Scenario graph extraction
- Transition graph parsing: `deposit→vote→withdraw`
- Declared prerequisite extraction
- Observed prerequisite matching
- Alignment index calculation
- Partial alignment detection
- Missing prerequisite detection
- Undocumented surface detection
- Findings without simulation support

**Example output:**
GovPoolAttackerMock.sol
Declared:  ARBITRARY_CALL, FLASH_LOAN_GOVERNANCE, GOVERNANCE_MANIPULATION, NO_SNAPSHOT
Observed:  ARBITRARY_CALL, NO_SNAPSHOT
Match: 2/4 🔸 partial_alignment

ACCESS_CONTROL_MISCONFIG — no simulation artifact found
AMM_SPOT_ORACLE — no simulation artifact found



</details>

<details>
<summary><b>🏗 12. Structural Profiling Engine</b></summary>

- Governance index
- Code pattern density index
- Liquidity risk index
- Holder concentration index
- Composite structural profile
- Density-based surface classification
- Expanded surface detection
- Architectural complexity scoring

</details>

<details>
<summary><b>🔐 13. Governance & Privilege Intelligence</b></summary>

- Arbitrary execution surface detection
- Proposal execution exposure
- Snapshot absence detection
- Flash-loan governance vector detection
- Role mutation exposure
- Upgrade authority mapping
- Proxy implementation transparency check

</details>

<details>
<summary><b>📡 14. Deployment Graph Awareness</b></summary>

- Multi-contract deployment mapping
- Factory lineage detection
- Proxy-to-logic mapping
- Cross-address relationship hints
- Contract classification
- Chain-specific deployment mapping

</details>

<details>
<summary><b>🧪 15. Cross-Layer Correlation Engine</b></summary>

- Static ↔ Onchain correlation
- Scenario ↔ Findings correlation
- Liquidity ↔ Oracle dependency correlation
- Holder ↔ Governance correlation
- Role surface ↔ Trust model correlation
- Behavioral ↔ Structural amplification
Code says timelock exists
→ Onchain: never deployed
→ Signal: GOVERNANCE_MISMATCH

Holders: 88% concentrated in Top-10
→ Governance: quorum = effectively 1 wallet
→ Signal: GOVERNANCE_CAPTURE_RISK

Thin DEX pool ($631K liquidity)
→ Spot oracle reads this pool
→ Signal: PRICE_MANIPULATION_FEASIBLE

Wash trading detected
→ Mint control exists in code
→ Signal: EXTRACTION_SETUP

“Fully decentralized DAO” in docs
→ Code: pause() + blacklist() + upgradeable proxy
→ Signal: NARRATIVE_MISMATCH

Attacker mock found in /test
→ No corresponding audit finding
→ Signal: UNDOCUMENTED_ATTACK_SURFACE



</details>

<details>
<summary><b>⏳ 16. Temporal Engine</b></summary>

- Role delta tracking
- Proxy upgrade delta
- Storage layout diff
- Holder concentration drift
- Liquidity migration detection
- Privileged surface mutation tracking
- Structural index drift

</details>

<details>
<summary><b>⚠️ 17. Derivatives Analysis — Binance · Bybit · OKX</b></summary>

Analyzes derivatives market structure to detect squeeze conditions, position crowding, and inorganic movements.

**Open Interest:**
- Open Interest aggregation (Binance, Bybit, OKX)
- OI velocity analysis
- OI vs price divergence detection
- OI vs volume ratio analysis
- OI vs market cap ratio analysis
- Cross-exchange OI distribution analysis
- OI concentration risk detection
- Synthetic leverage density estimation
  - leverage buildup
  - crowding
  - leverage imbalance
  - unstable positioning

**Positioning Intelligence:**
- Funding Rate Intelligence
- Long / Short Positioning Intelligence
- Aggressor Flow Intelligence
- Cross-Exchange Derivatives Correlation
- Derivatives regime classification

**Risk Modeling:**
- Orderbook Liquidity Intelligence
- Liquidation Risk Modeling
- Temporal Derivatives Tracking

**Detects:** `leverage buildup` · `crowded positioning` · `squeeze setups` · `cascade risk` · `manipulation conditions`

</details>

---

## Continuous Radar — 24/7

<details>
<summary><b>📡 GitHub Radar</b></summary>

Real-time new repository monitoring.

- Scores repos across 20+ signals
- Detects: governance risk patterns, admin functions, flash-loan vectors, force-push activity
- Auto-launches scanner on top findings
- Background task queue with instant alerts (BLACKBOX tier)

</details>

<details>
<summary><b>📊 DeFiLlama Radar</b></summary>

New protocol detection across DeFi ecosystem.

- TVL filtering and category tagging
- GitHub repository discovery
- CoinGecko enrichment
- Multi-source: DeFiLlama API + CoinGecko + protocol homepage

</details>

<details>
<summary><b>🔍 Verified Contract Radar</b></summary>

New verified on-chain contracts.

- RPC + Etherscan V2 API
- Chains: ETH · BSC · Polygon · Arbitrum · Base · Optimism
- Automatic junk / tutorial / student contract filtering

</details>

<details>
<summary><b>🌐 Stellar / Soroban Radar</b></summary>

Specialized Stellar ecosystem monitoring.

- New assets via Horizon API
- SDEX orderbook monitoring
- Scam factory detection
- Issuer cluster analysis

</details>

---
# BORIS — Example Reports

Real outputs from BORIS CLI. Protocol names redacted.
All data reflects actual scan results — nothing fabricated.

---

| Module | Example | Key finding |
|--------|---------|-------------|
| 🔥 BLACKBOX (Full) | [Governance Protocol](full-report/sample-governance-protocol.md) | Flash-loan governance · 48 findings outside audit scope · 4 exploit chains |
| 🌐 Soroban Radar | [Stellar Scam Scan](soroban-radar/stellar-scam-scan.md) | 52 scams in 358 assets · 2 factory networks · $0 oracle cost |
| 💰 Funds Flow | [Pool Analysis](funds-flow/sample-pool-analysis.md) | Wash trading 85/100 · 13 signals · volume inflation confirmed |
| 📊 Market Engine | [Market Scan](market-scan/sample-market-engine.md) | OI/Depth 26x squeeze · GitHub abandoned 444d · smart money divergence |
| 🐋 Holders | [Holder Distribution](holders/sample-holders-analysis.md) | 59.45% single contract · Top-10 real 88.3% · governance capture threshold |
| 🛰 Social | [Social Intelligence](social/sample-social-intelligence.md) | 5 impersonators · 1.0% TG engagement · 315K X followers hollow |

---

> All outputs are from BORIS beta 1.3 CLI.
> Telegram bot produces the same intelligence in structured report format.
> No fabricated data. No cherry-picked examples. Real scan, real protocol, names redacted.
---

> Outputs are from BORIS beta 1.3 CLI.
> Telegram bot produces the same intelligence in structured report format.
## On-Chain Intelligence Modules

| Module | What it does |
|--------|-------------|
| **Funds Flow Analyzer** | Wash trading · bot patterns · drain detection · CEX vs owner extraction |
| **Address Profiler** | Address classification · role context · cross-chain fingerprinting |
| **Holders Analyzer** | Distribution · whale mapping · governance concentration · LP correction |

**Supported chains:** EVM (ETH · BSC · Polygon · Arbitrum · Base · Optimism) · Solana · Tron · Stellar

---

## Social Intelligence

**Platforms:** Telegram · Twitter/X · Discord

| Signal | Detection |
|--------|-----------|
| Subscriber count vs engagement | Dead community |
| Post reaction / coverage ratio | Hollow engagement |
| Content analysis | Scam / shill / signal / pump patterns |
| Channel age vs project age | Astroturfing |
| Account creation context | Coordinated launch |
| Follower / following ratio | Bot army |
| Server age + verification level | Discord trust baseline |

- Impersonation detection (Levenshtein + pattern matching)
- Cross-platform consistency scoring
- Risk score (0–100) + Trust score (0–100)
- Official vs ecosystem vs impersonator separation

**Example output:**  
`🚨 Impersonators: 5 detected`  
`@ххххх_network_official_chats → @хххх_network_official_chat`  
`📨 15 channels (2 official) · 92,749 subscribers · anomalous engagement`

---

## Real Report — What BLACKBOX Produces
🔥 BLACKBOX REPORT
Target: [Protocol] | Deploy: YES | Audits: 6 | Last: 549d ⚠️ STALE

ARCHETYPE: DAO / Governance (90%)
Claimed: DAO
Observed: restricted role cluster with broad execution authority
⚠️ Narrative mismatch detected

CODE PATTERNS: 269 total
🔴 CRITICAL: 5  🟠 HIGH: 3  🟡 MEDIUM: 60  ⚪ LOW: 58
36 patterns normalized by archetype (DAO_GOVERNANCE)

🔴 NO_SNAPSHOT ×3       GovPool.sol:218 · GovValidators.sol:117 · GovPoolVote.sol:29
🔴 ARBITRARY_CALL ×3    DistributionProposal.sol:65 · GovUserKeeper.sol:795
🟠 EMERGENCY_DRAIN      TokenSaleProposal.sol:18
🟠 ACCESS_CONTROL       PoolRegistry.sol

EXPLOIT CHAINS:
Chain #1: Flash-loan governance [Score: 67 | Confidence: 75%]
Step 1: Flash-loan governance token — no snapshot protection
Step 2: Vote with flash-loaned balance
Step 3: Execute arbitrary call via passed proposal
Amplifiers: SOCIAL_WEAK · FLOW_MANIPULATION · HOLDERS_CONCENTRATED · STALE_AUDIT

DEPLOYMENT: 31 contracts — ARB · BSC · ETH · POLYGON
Factory lineage: CoreProperties → GovPool → GovToken → GovUserKeeper

AUDIT DRIFT:
Was: C3/H2 → Now: C5/H45
Still present: 4 | Fixed: 10 | New outside scope: 48
Mock alignment: 2/4 prerequisites matched (partial)

HOLDERS: 🔴 extreme
Top-10: 93.4% | Real (CEX/LP corrected): 88.3%
#1: 59.5% (contract) · #2: Binance Hot Wallet 5.8%

LIQUIDITY: $631,999 | Organic: ~20% | Cyclic sequences: 80/100

SOCIAL:
Impersonators: 5 detected
Dead channels: 3 | Anomalous engagement flagged

STRUCTURAL PROFILE:
🔴 Governance risk:        95/100
🔴 Liquidity risk:         80/100
🔴 Holder concentration:   75/100
🟡 Code pattern density:   46/100
🟡 Social trust:           48/100



---

## Tiers

|  | 👁️ GUEST | 🟥 RADAR | 📋 RAW | 🔥 BLACKBOX |
|--|:--:|:--:|:--:|:--:|
| **Price** | Free | $19/mo | $29/mo | $49/mo |
| **Scans / day** | 3 | 25 | 30 | Unlimited |
| **Parallel scans** | 1 | 1 | 1 | 2 + queue 5 |
| | | | | |
| **Summary** | ✓ | ✓ | ✓ | ✓ |
| **Risk categories + severity** | — | ✓ | ✓ | ✓ |
| **Governance analysis** | — | ✓ | ✓ | ✓ |
| **Admin control score** | — | ✓ | ✓ | ✓ |
| **Behavioral score (aggregated)** | — | ✓ | ✓ | ✓ |
| **Audit context (presence, age, coverage)** | — | ✓ | ✓ | ✓ |
| | | | | |
| **Full findings + file:line** | — | — | ✓ | ✓ |
| **Archetype + governance model** | — | — | ✓ | ✓ |
| **Holders / liquidity / deployments** | — | — | ✓ | ✓ |
| **CEX listings** | — | — | ✓ | ✓ |
| **Raw technical dump — no verdicts** | — | — | ✓ | ✓ |
| | | | | |
| **Exploit paths + attack vectors** | — | — | — | ✓ |
| **Audit drift (full)** | — | — | — | ✓ |
| **Deploy trace analysis** | — | — | — | ✓ |
| **Code fragments + exact location** | — | — | — | ✓ |
| **Social intelligence** | — | — | — | ✓ |
| **Funds Flow Intelligence** | — | — | — | ✓ |
| **Address Profiler** | — | — | — | ✓ |
| | | | | |
| **Discovery feed access** | — | ✓ | ✓ | ✓ |
| **Continuous Radar 24/7** | — | ✓ | ✓ | ✓ |
| **DeFiLlama scanner 24/7** | — | ✓ | ✓ | ✓ |
| **Alerts** | — | Batched 12–24h | Batched 12–24h | Instant |
| **JSON export** | — | Summary | Full technical | Full |
| **Beta access** | — | — | — | First |

> 👁️ **GUEST** — entry map. See the surface.  
> 🟥 **RADAR** — pressure map. Understand the risk structure.  
> 📋 **RAW** — data map. No scores, no verdicts. Pure technical dump for people who read code, not conclusions.  
> 🔥 **BLACKBOX** — consequence map. Exploit paths, drift, full intelligence stack.

---

## Quick Start
Open @BlackOracleBORIS_bot on Telegram
/start
Drop a contract address, GitHub repo URL, or token ticker
Receive your report


**Accepted inputs:**
- `owner/repo` or `https://github.com/...` — GitHub repository
- `0x...` — EVM contract address
- Explorer URLs (Etherscan, BscScan, Arbiscan, etc.)
- `TOKEN` — ticker (market + derivatives scan)

No setup. No API keys. No CLI.

---

## Philosophy
BORIS does not judge projects.
BORIS maps control and capital mobility.

BORIS does not rate safety.
BORIS measures exposure.

BORIS does not predict collapse.
BORIS identifies structural pressure points.



FUD makes claims.  
BORIS makes observations.

`"Treasury callable via governance without timelock"` — not FUD.  
That is a structural fact.

---

## Docs

- [`docs/architecture.md`](docs/architecture.md) — full system architecture
- [`docs/signals.md`](docs/signals.md) — signal list and weights
- [`docs/tiers.md`](docs/tiers.md) — tier breakdown
- [`examples/sample_report.md`](examples/sample_report.md) — example BLACKBOX report
- [`examples/sample_market.md`](examples/sample_market.md) — example market scan
- [`CHANGELOG.md`](CHANGELOG.md) — version history

---

## Links

| | |
|---|---|
| 🤖 Bot | [@BlackOracleBORIS_bot](https://t.me/BlackOracleBORIS_bot) |
| 📡 Channel EN | [t.me/Black_Oracle_BORIS_eng](https://t.me/Black_Oracle_BORIS_eng) |
| 📡 Channel RU | [t.me/Black_Oracle_BORIS_ru](https://t.me/Black_Oracle_BORIS_ru) |
| 🐦 Twitter/X | [@BlackOracleRoot](https://x.com/BlackOracleRoot) |

---

<div align="center">

*Not investment advice. Not a guarantee. Not "scam / not scam".*

**BORIS shows where the lever is.**

</div>
