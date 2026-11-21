<div align="center">

<img src="boris_logo.png" alt="BORIS" width="320"/>

# BORIS Beta v 1.44
### Black Oracle Risk Inspection System
**Deterministic 20-Layer Threat Surface Intelligence + AI Dossier Interpreter for Web3 Protocols.**

*Code doesn't lie. Narratives do.*

[![Web Terminal](https://img.shields.io/badge/Web_Terminal-black--oracle.com-e11d48?style=flat&logo=cloudflare&logoColor=white)](https://black-oracle.com)
[![Bot](https://img.shields.io/badge/Telegram-Bot-2CA5E0?style=flat&logo=telegram)](https://t.me/BlackOracleBORIS_bot)
[![Support](https://img.shields.io/badge/Support-@V__swarm-2CA5E0?style=flat&logo=telegram)](https://t.me/V_swarm)
[![Twitter](https://img.shields.io/badge/Twitter-@BlackOracleRoot-000000?style=flat&logo=x)](https://x.com/BlackOracleRoot)

![Status](https://img.shields.io/badge/status-live_v1.44-brightgreen)
![AI Cortex](https://img.shields.io/badge/Roadmap_v1.5-AI_Cortex_%26_Swarm_%5BSOON%5D-e11d48)
![Layers](https://img.shields.io/badge/architecture-20%20layers%20%7C%2015%20engines%20%7C%206%20radars-blue)
![OSPEC](https://img.shields.io/badge/OSPEC-1.14M%20findings%20%7C%207%2C087%20REAL-orange)
![Languages](https://img.shields.io/badge/languages-12-orange)
![Intelligence](https://img.shields.io/badge/corpus-289k%2B%20targets%20%7C%2020.8k%20audits%20%7C%202.5k%20exploits-red)
![Chains](https://img.shields.io/badge/chains-EVM%20%7C%20Solana%20%7C%20Tron%20%7C%20Stellar%2FSoroban%20%7C%20TON%20%7C%20Move-orange)

</div>

---

> ### ⚠️ Active Development — Beta v 1.44
> BORIS is a live, continuously evolving sovereign intelligence system (**[black-oracle.com](https://black-oracle.com)** + **[@BlackOracleBORIS_bot](https://t.me/BlackOracleBORIS_bot)**).
> Documentation reflects the production v1.44 architecture.
> **If something is missing — it's being built. If something is wrong — it's being fixed.**

---

## ⚡ What's New in BORIS Beta v 1.44 (& Roadmap v 1.5)

### 1. 🧠 Powered by AI — BORIS Neural Cortex & Agent Swarm (`SOON in v1.5 · RAW+ Tiers`)
First-generation "AI security scanners" failed because they fed raw `.sol` files directly into an LLM and asked it to guess vulnerabilities — producing hallucinations, missed storage collisions, and fabricated findings.

**BORIS is built on the opposite principle: Deterministic Execution First, Neural Interpretation Second.**
1. **The Mechanical Hammer (20 Deterministic Layers — `LIVE in v1.44`):** Specialized static, on-chain, cryptographic, and secret-harvesting engines inspect the protocol across **20 layers** — multi-language ASTs, live `eth_getStorageAt` EIP-1967 proxy slots, BN254 elliptic-curve math for ZK Groth16 verifiers, **OSPEC secret & key leak intelligence**, post-audit Git commit drift, whale concentration, 14-day funds flow, and CEX/DEX derivatives microstructure — emitting a **strict, verified JSON evidence dossier** (available across all tiers).
2. **Grounded Institutional Memory (`LIVE in v1.44`):** Every scan is cross-referenced against BORIS's local databases: **20,826 completed engineering audits**, **2,539 historical exploit post-mortems & Foundry PoCs**, and **289,000+ indexed radar targets**.
3. **BORIS Neural Cortex & Autonomous Swarm (`SOON in v1.5 · from RAW+ tier`):** While `GUEST` and `RADAR` tiers receive the deterministic report, `RAW` and `BLACKBOX` operators unlock the AI Dossier Interpreter (which translates verified JSON telemetry + matched historical precedents into human intelligence with 0% raw-code hallucination) and personal **Agent Swarm Control** to dispatch autonomous inspection swarms across custom targets.

### 2. 🌐 Full Web SaaS Terminal — [black-oracle.com](https://black-oracle.com)
Alongside the Telegram terminal, BORIS v1.44 launches a full browser-based intelligence workstation:
- **15 Interactive Intelligence Engines** in the Operator Cabinet (`/dashboard`):
  1. **Cross-Chain Bridge Radar & Validator Inspector** (5,731+ contracts indexed across 18 chains, on-chain TVL via Ankr Multichain API, bytecode vulnerability signatures: Emergency Drain, Arbitrary Call, EIP-1967 Proxy, Replay, and 110 historical bridge exploit post-mortems & Foundry PoCs)
  2. **Holders & Whales** (Top-10 concentration, CEX/LP/bridge normalization)
  2. **Market & Derivatives** (`/market` — Open Interest, Funding, Long/Short, $\pm 2\%$ orderbook depth, manipulation & squeeze scoring)
  3. **14-Day Funds Flow** (wash-trading cycles, coordinated bot clusters, mixer/bridge attribution)
  4. **Social & OSINT** (GitHub/X/Telegram/Discord cross-verification & impersonator detection)
  5. **Soroban / Stellar SIM** (WASM contract analysis, `AUTH_CLAWBACK`/`AUTH_REVOCABLE` flags, SDEX depth & VWAP manipulation cost)
  6. **OSPEC Secret & Config Intelligence** (`1,144,698` scanned findings across `31,837` repos, L2.5-filtered to `7,087` verified `REAL` secrets and `550` `LIVE` keys with drill-down occurrences)
  7. **2,539 Exploits & Foundry PoC Corpus** (`1,678` deep technical writeups with full Foundry tests + `861` structured incidents, dual `0x`-contract matcher and keyword search)
  8. **Deployer & Address Profiler** (`AddressIntelligence` + batch `DeployAnalyzer` creator wallet forensics)
  9. **Proxy & EIP-1967 Storage Inspector** (`implementation`, `admin`, `beacon`, legacy OZ slots + uninitialized `initialize()` probing)
  10. **Flash-Loan & Spot-Oracle Detector** (`slot0`/`getReserves` spot reads vs TWAP/Chainlink defenses + cross-chain bridge bytecode signatures)
  11. **Web3 Surface Mapper** (parallel 18-subdomain recon + frontend JS bundle contract/RPC/sourcemap extraction)
  12. **Post-Audit Git Drift** (automatic PDF audit parsing in `audits/` + Git commit drift since last audit date)
  13. **ZK Groth16 Verifier Auditor** (BN254 curve/subgroup soundness, $\gamma == \delta$, Frozen Heart, and fingerprint matching against `4,982` on-chain verifiers)
  14. **Matrix Sandbox v16.2** (kernel-level `sys.addaudithook` + `_BlockedImportFinder` isolated Python/Web3 execution with `BLOCKED / SIMULATED / EXECUTED` telemetry)
- **6 Live 24/7 Radar Streams** with server-side pagination: `GitHub Radar (33,424 repos)`, `DeFiLlama Radar (9,420 protocols + 1-click Enricher)`, `Verified Contracts (246,007 across 5 EVM chains)`, `Soroban Radar (641 targets)`, `ZK Verifier Radar (4,982 verifiers)`, and `Archive Dossiers (20,826 instant reports)`.
- **Unified Web ↔ Telegram Sync & Sovereign Billing:** 1-click `tg://resolve` account/history synchronization and zero-middleman **BIP-44 HD multi-chain checkout** across 7 networks (`Arbitrum`, `Base`, `BSC`, `Polygon`, `Ethereum`, `TRON`, `Solana`) + `@CryptoBot`.

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
<td colspan="7" align="center">

**20-LAYER CROSS-CORRELATION ENGINE + OSPEC + BORIS NEURAL CORTEX**  
`Code ↔ Proxy Storage ↔ ZK Math ↔ OSPEC Secrets ↔ Holders ↔ Funds Flow ↔ Derivatives ↔ Historical Exploits`

</td>
</tr>
<tr>
<td align="center">📦<br/><b>STATIC</b><br/><sub>12 languages<br/>AST + Bytecode</sub></td>
<td align="center">🔎<br/><b>ONCHAIN</b><br/><sub>EIP-1967 · ABI<br/>Deployer</sub></td>
<td align="center">🔐<br/><b>ZK & SANDBOX</b><br/><sub>Groth16 BN254<br/>Matrix v16.2</sub></td>
<td align="center">🗝️<br/><b>OSPEC</b><br/><sub>1.14M Findings<br/>7,087 REAL · 550 LIVE</sub></td>
<td align="center">⚠️<br/><b>MARKET</b><br/><sub>Spot · OI<br/>Derivatives</sub></td>
<td align="center">📡<br/><b>RADAR 24/7</b><br/><sub>289k+ Targets<br/>20.8k Audits</sub></td>
<td align="center">🧠<br/><b>AI & SWARM</b><br/><sub>v1.5 (RAW+)<br/>Interpreter</sub></td>
</tr>
<tr>
<td colspan="7" align="center">

**TEMPORAL & PRECEDENT ENGINE** — `Role Δ · Upgrade Δ · Holder Drift · OI Δ · Post-Audit Git Drift · 2,539 Exploit Signatures`

</td>
</tr>
</table>

---

## Capability Matrix (20 Layers)

<details>
<summary><b>📦 1. Static Code Analysis — 12 languages, multi-engine + custom AST detectors</b></summary>

**Languages:**  
`Solidity` · `Vyper` · `Rust (Solana/Anchor, Soroban, Near)` · `Move (Aptos/Sui)` · `TON (FunC/Tact/Fift)` · `Go` · `Python` · `Java` · `C++` · `TypeScript` · `Elixir` · `Shell`

**Engines:** Slither · Mythril · Aderyn · Semgrep + proprietary structural & invariant detectors

| Pattern | Severity |
|---------|----------|
| Reentrancy (standard + cross-function + read-only) | CRITICAL |
| Delegatecall misuse | CRITICAL |
| Arbitrary call surface | CRITICAL |
| Emergency drain patterns | CRITICAL |
| Uninitialized proxy / implementation `initialize()` | CRITICAL |
| Unchecked transfer / return | HIGH |
| Oracle spot-price dependency (`slot0` / `getReserves` without TWAP) | HIGH |
| Mint / burn without bounds | HIGH |
| Proxy upgrade surface in single EOA | HIGH |
| Storage layout collision | HIGH |
| Flash-loan governance vectors | MEDIUM |
| Privileged role escalation | MEDIUM |

- Precise `file:line` mapping for every finding
- Custom risk taxonomy correlated against 2,539 historical exploit signatures
- Pattern classification: CRITICAL / HIGH / MEDIUM / LOW / INFO

</details>

<details>
<summary><b>🔎 2. Onchain Structural & EIP-1967 Proxy Analysis</b></summary>

**Chains:** Ethereum · BSC · Polygon · Arbitrum · Base · Optimism · Solana · Tron · Stellar/Soroban

**Proxy Resolution:**
- Direct `eth_getStorageAt` inspection of ERC1967 (`implementation`, `admin`, `beacon`), UUPS, Transparent Proxy, and legacy OpenZeppelin slots
- Implementation discovery & bytecode selector extraction
- Uninitialized `initialize()` simulation probing (`uninit_proxy_scan`)
- Storage layout inspection + collision detection

**Role & Control Mapping:**
- Privileged role extraction & EOA vs Multisig/Timelock attribution
- Admin function surface mapping: `pause` / `blacklist` / `emergencyWithdraw` / `upgradeTo`
- Creator/Deployer wallet forensics (`AddressIntelligence` + `DeployAnalyzer`)
- Multi-contract linkage: factory → router → vault → token

</details>

<details>
<summary><b>🧠 3. Archetype Normalization — false positive reduction</b></summary>

Reduces false positives through architectural context.

- Stablecoin normalization — `blacklist` / `mint` / `freeze` flagged as by design
- DEX normalization — LP mint/burn, spot oracle patterns flagged as by design
- Liquidity staking normalization
- Governance protocol normalization
- LP pair & Router normalization
- Factory-driven architecture context

> Findings are scored against protocol archetype before surfacing.  
> A `blacklist()` in a stablecoin is not a backdoor. In a gaming token, it is.

</details>

<details>
<summary><b>🔗 4. Exploit Chain Modeling — Invariant Correlation Engine + 2,539 Exploits Corpus</b></summary>

Isolated findings become real attack paths.

- Prerequisite-based scenario modeling
- Multi-step exploit chain modeling
- Cross-reference against **2,539 historical exploits** (`1,678` deep writeups with Foundry PoCs + `861` DeFiHackLabs incidents)
- Flash-loan scenario simulation (logical)
- Governance capture & oracle manipulation chains
- Bridge bytecode signature detection (`UPGRADE`, `ARBCALL`, `DRAIN`, `FLASH`, `REPLAY`)
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

- Holder distribution index & Top-10 concentration
- Real concentration correction — pools / CEX normalization
- Whale, contract, and proxy holder classification
- LP concentration & extreme single holder detection
- Governance concentration heuristics

**Sources:** Etherscan V2 (rotated key pool) · BscScan · Blockscout · Helius (Solana) · Rugcheck · Tronscan

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
<summary><b>🛰 9. Behavioral & 14-Day Funds Flow Layer</b></summary>

- 14-day transaction graph & flow clustering (`funds_flow_analyzer`)
- Cyclic swap & wash-trading loop detection
- Concentrated trader & coordinated bot-cluster detection
- Temporal activity spikes & liquidity event correlation
- Trader dominance scoring

</details>

<details>
<summary><b>📉 10. Post-Audit Git Drift Analysis</b></summary>

Audits are snapshots. BORIS tracks what changed after.

- Automatic PDF/Markdown audit report parsing inside `audits/` (`UnifiedAuditAnalyzer`)
- Full Git commit history analysis after the last audit date (`GitDriftAnalyzer`)
- Repo vs deployed bytecode divergence
- Pattern delta, severity drift, and prerequisite drift tracking
- Structural surface expansion & quantitative **Audit Drift Score**

**Supported audit firms:** OpenZeppelin · Trail of Bits · Sherlock · Code4rena · Cyfrin · Spearbit · Cantina · Hacken · Ambisafe

**Example output:**
```
Audits: 6 | Last: 2024-08-30 (549d) ⚠️ STALE
Was: C3/H2 → Now: C5/H45
Still present: 4 | Potentially fixed: 10 | New (outside audit scope): 48
Files outside audit coverage: GovUserKeeper.sol · GovValidators.sol · GovPool.sol
```

</details>

<details>
<summary><b>🎭 11. Mock / Attack Simulation Correlation</b></summary>

BORIS detects attacker mock contracts in the repo and correlates them with real findings.

- Attacker mock detection
- Scenario graph extraction & transition graph parsing: `deposit→vote→withdraw`
- Declared vs observed prerequisite matching
- Alignment index calculation & undocumented surface detection

**Example output:**
```
GovPoolAttackerMock.sol
Declared:  ARBITRARY_CALL, FLASH_LOAN_GOVERNANCE, GOVERNANCE_MANIPULATION, NO_SNAPSHOT
Observed:  ARBITRARY_CALL, NO_SNAPSHOT
Match: 2/4 🔸 partial_alignment
```

</details>

<details>
<summary><b>🏗 12. Structural Profiling & Web3 Surface Mapping</b></summary>

- Governance, Code pattern density, Liquidity risk, and Holder concentration indices
- **Web3 Surface Mapper:** parallel reconnaissance across 18 protocol subdomains (`app`, `api`, `rpc`, `graphql`, `admin`, `staging`, `bridge`)
- Extraction of hardcoded `0x` contract addresses, RPC endpoints, and exposed `.map` source maps from frontend JS bundles

</details>

<details>
<summary><b>🔐 13. Governance & Privilege Intelligence</b></summary>

- Arbitrary execution surface detection
- Proposal execution exposure
- Snapshot absence & flash-loan governance vector detection
- Role mutation exposure & upgrade authority mapping

</details>

<details>
<summary><b>📡 14. Deployment Graph & Creator Forensics</b></summary>

- Multi-contract deployment mapping & factory lineage detection
- Proxy-to-logic mapping
- **Deployer & Address Profiler:** automated profiling of the creator wallet (`creator_profile`: age, balance, sibling deployments)

</details>

<details>
<summary><b>🧪 15. Cross-Layer Correlation Engine</b></summary>

- Static ↔ Onchain correlation
- Scenario ↔ Findings correlation
- Liquidity ↔ Oracle dependency correlation
- Holder ↔ Governance correlation
- Role surface ↔ Trust model correlation

```
Code says timelock exists
→ Onchain: never deployed
→ Signal: GOVERNANCE_MISMATCH

Holders: 88% concentrated in Top-10
→ Governance: quorum = effectively 1 wallet
→ Signal: GOVERNANCE_CAPTURE_RISK

Thin DEX pool ($631K liquidity)
→ Spot oracle reads this pool
→ Signal: PRICE_MANIPULATION_FEASIBLE

“Fully decentralized DAO” in docs
→ Code: pause() + blacklist() + upgradeable proxy
→ Signal: NARRATIVE_MISMATCH
```

</details>

<details>
<summary><b>⏳ 16. Temporal Engine</b></summary>

- Role delta & proxy upgrade delta tracking
- Storage layout diff & holder concentration drift
- Liquidity migration & structural index drift

</details>

<details>
<summary><b>⚠️ 17. Derivatives Analysis — Binance · Bybit · OKX</b></summary>

Analyzes derivatives market structure to detect squeeze conditions, position crowding, and inorganic movements.

- **Open Interest:** cross-exchange aggregation, OI velocity, OI/volume & OI/mcap ratios, synthetic leverage density
- **Positioning Intelligence:** Funding Rate, Long/Short Positioning, Aggressor Flow, Cross-Exchange Correlation
- **Risk Modeling:** Orderbook Liquidity Intelligence ($\pm 2\%$), Liquidation Risk Modeling, Temporal Derivatives Tracking

**Detects:** `leverage buildup` · `crowded positioning` · `squeeze setups` · `cascade risk` · `manipulation conditions`

</details>

<details>
<summary><b>🔐 18. ZK Intelligence Engine — 26 detectors, 55+ vulnerability classes, 4,982 On-Chain Verifiers</b></summary>

Automated zero-knowledge verifier analysis. Source + bytecode.

- **Analysis:** VK Soundness ($\gamma==\delta$, generator validation, zero checks), Curve Math ($G_1/G_2$ membership on BN254, 5 $G_2$ conventions), Protocol Logic (nullifier reuse, root validation), Signal Binding, IC/Pairing poisoning/truncation/overflow, Bytecode VK extraction without source, Proof Forgery (Frozen Heart, malleability, negation), Setup Forensics.
- **ZK Radar (`zk_radar_v4.db`):** persistent fingerprint database across **4,982 on-chain Groth16 verifiers** (ETH · BSC · Polygon · Arbitrum · Base · Optimism) with VK reuse cluster discovery and archetype classification (`TORNADO_MIXER` · `SEMAPHORE_IDENTITY` · `MACI_VOTING` · `ZK_ROLLUP` · `AZTEC_PRIVACY`).

</details>

<details>
<summary><b>🛡️ 19. Web3 Surface Mapper & Matrix Sandbox v16.2</b></summary>

- **Web3 Surface Mapper (`web3_surface_mapper`):** parallel reconnaissance across 18 protocol subdomains (`app`, `api`, `rpc`, `graphql`, `admin`, `staging`, `bridge`, `docs`) with automated extraction of hardcoded `0x` contract addresses, private RPC endpoints, and exposed `.map` source maps from frontend JS bundles.
- **Matrix Sandbox v16.2 (`matrix_sandbox_v16_2`):** isolated child-process execution engine for untrusted Python/Web3 helpers and PoCs using kernel-level `sys.addaudithook` and `_BlockedImportFinder`, blocking secret file access and simulating network/process calls (`MockSocket`, `MockSession`, `MockPopen`) with strict `BLOCKED / SIMULATED / EXECUTED` telemetry.

</details>

<details>
<summary><b>🗝️ 20. OSPEC — Oracle SPECtrum (Secret, Key & Infrastructure Leak Intelligence)</b></summary>

Continuous automated discovery, cryptographic verification, and on-chain enrichment of leaked secrets across Web3 repositories and deployment configurations.

**Scale & Coverage:**
- **31,837+ Web3 repositories** scanned continuously (`1,144,698` indexed raw findings in `harvester.db`)
- **7,087 verified `REAL` secrets** across `777` repositories after L2.5 anti-FP filtering
- **550 `LIVE` verified keys** with active on-chain balances, nonces, or live RPC/API responses

**Multi-Stage Cryptographic Validation (`l2_validators_v2` + `l2_coverage` + `kind_rules`):**
- **Cryptographic Key Verification:** `secp256k1` scalar range & address derivation (`hex_privkey`), `ed25519` curve point verification (`solana_keypair_array`, context-gated `solana_seed_hex`), `BIP-39` 2048-word dictionary & entropy checksum verification (`bip39_mnemonic`), `eth_keystore_v3` JSON structure & MAC validation, `PEM` ASN.1 DER structure checks, `NEAR` `ed25519:` base58 keys, and `Stellar` `S...` CRC16-XModem seeds.
- **On-Chain & EIP-7702 Live Enrichment (`l5_live_key_detector`):** automatic multi-chain balance (`balance_wei`), transaction count (`nonce`), and **EIP-7702 delegation (`0xef0100 || delegate_addr`)** inspection across Ethereum, Arbitrum, Base, Optimism, Polygon, BSC, and Solana.
- **Infrastructure & RPC/API Probing:** Alchemy v2, Infura project URLs, QuickNode, Ankr, Etherscan keys, GitHub PATs (`ghp_`/`github_pat_`), AWS `AKIA`, GCP Service Accounts, PostgreSQL/MongoDB/Redis connection URIs, JWTs, Telegram bot tokens, and Slack/Discord tokens.
- **L2.5 False-Positive Elimination:** automatic filtering of Hardhat/Anvil/Foundry test accounts (`known_test_addrs`), SHA-256 checksum manifests, placeholder strings, and documentation vectors.

</details>

---

## Continuous Radar — 24/7 (`289,000+` Indexed Targets)

<details>
<summary><b>📡 GitHub Radar — 33,424+ Repositories [FREE]</b></summary>

- Real-time Web3 repository discovery scored across 20+ structural signals
- Detects governance risk patterns, admin functions, flash-loan vectors, and force-push activity
- Synchronized with the **20,826 pre-computed engineering dossiers** in `AUDITS_BASE`

</details>

<details>
<summary><b>📊 DeFiLlama Radar — 9,420+ Protocols [RADAR+]</b></summary>

- Continuous protocol discovery across the DeFi ecosystem with TVL filtering and category tagging
- **1-Click Protocol Enricher:** instant resolution of protocol GitHub repositories, smart contracts, and social links

</details>

<details>
<summary><b>🔍 Verified Contract Radar — 246,007+ Contracts [RADAR+]</b></summary>

- Continuous indexing of newly verified contracts across ETH · Base · Polygon · BSC · Arbitrum · Optimism
- Automatic junk / tutorial / student contract filtering

</details>

<details>
<summary><b>🌐 Stellar / Soroban Radar — 641+ Targets [RADAR+]</b></summary>

- Specialized Stellar asset and Soroban WASM contract monitoring via Horizon API
- SDEX orderbook monitoring, scam factory detection, and issuer cluster analysis

</details>

<details>
<summary><b>🔐 ZK Verifier Radar — 4,982+ On-Chain Verifiers [RAW+]</b></summary>

- Pairing precompile detection (`0x08 STATICCALL`) and bytecode VK extraction without source code
- Cross-chain VK reuse cluster discovery (`zk_radar_v4.db`)

</details>

<details>
<summary><b>🗝️ OSPEC Secret Harvester — 31,837+ Repos / 7,087 Verified REAL Secrets [RADAR+]</b></summary>

- Continuous background scanning of newly discovered GitHub repositories (`radar_watcher.py`)
- Multi-stage L2.5 cryptographic validation (`63/63` automated self-tests) separating real credentials (`REAL`) from test vectors (`TEST`)
- Live EVM/Solana address derivation, balance/nonce checking, and repository-grouped drill-down in both Telegram (`/ospec`) and Web Terminal (`/dashboard`)

</details>

---

# BORIS — Example Reports

Real outputs from BORIS. Protocol names redacted.  
All data reflects actual scan results — nothing fabricated.

| Module | Example | Key finding |
|--------|---------|-------------|
| 🔥 BLACKBOX | [Governance Protocol](examples/full-report/sample-governance-protocol.md) | Flash-loan governance · 48 findings outside audit scope |
| 🌐 Soroban Radar | [Stellar Scam Scan](examples/soroban-radar/stellar-scam-scan.md) | 52 scams · $0 oracle cost · 2 factory networks |
| 💰 Funds Flow | [Pool Analysis](examples/funds-flow/sample-pool-analysis.md) | Wash trading 85/100 · 13 signals |
| 📊 Market Engine | [Market Scan](examples/market-scan/sample-market-engine.md) | OI/Depth 26x squeeze · GitHub 444d abandoned |
| 🐋 Holders | [Holder Distribution](examples/holders/sample-holders-analysis.md) | 59.45% single contract · governance capture threshold |
| 🛰 Social | [Social Intelligence](examples/social/sample-social-intelligence.md) | 5 impersonators · 1.0% TG engagement |

> All outputs are produced by the BORIS deterministic engine.  
> Both the **[Web Terminal (`black-oracle.com`)](https://black-oracle.com)** and **[@BlackOracleBORIS_bot](https://t.me/BlackOracleBORIS_bot)** deliver full structured intelligence.

---

## Real Report — What BLACKBOX Produces
```
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
```

## Docs
- [`CHANGELOG.md`](CHANGELOG.md) — version history

---

## Tiers (`black-oracle.com` & `@BlackOracleBORIS_bot`)

|  | 👁️ GUEST | 🟥 RADAR | 📋 RAW | 🔥 BLACKBOX |
|--|:--:|:--:|:--:|:--:|
| **Price** | Free | $19/mo ($171/yr) | $29/mo ($261/yr) | $49/mo ($441/yr) |
| **Scans / day** | 3 | 25 | 50 | Unlimited |
| **Parallel scans** | 1 | 1 | 1 | 2 + queue 5 |
| | | | | |
| **Summary & Surface Verdicts** | ✓ | ✓ | ✓ | ✓ |
| **Risk categories + severity** | — | ✓ | ✓ | ✓ |
| **Governance & Admin control score** | — | ✓ | ✓ | ✓ |
| **Behavioral score + Audit context** | — | ✓ | ✓ | ✓ |
| **12 Web Intelligence Engines (OSPEC, 2.5k Exploits, Proxy, Drift, Surface, Flash)** | — | ✓ | ✓ | ✓ |
| | | | | |
| **Full findings + `file:line`** | — | — | ✓ | ✓ |
| **Archetype + governance model** | — | — | ✓ | ✓ |
| **Holders / liquidity / deployments** | — | — | ✓ | ✓ |
| **ZK Groth16 Verifier Auditor + Matrix Sandbox v16.2** | — | — | ✓ | ✓ |
| **Raw technical dump — no verdicts** | — | — | ✓ | ✓ |
| | | | | |
| **Exploit paths + attack vectors** | — | — | — | ✓ |
| **Audit drift (full) + Deploy trace** | — | — | — | ✓ |
| **Code fragments + exact location + Unmasked OSPEC secrets** | — | — | — | ✓ |
| **BORIS Neural Cortex & Swarm (v1.5)** | Deterministic Report | Deterministic Report | AI Dossier Interpreter *(Soon)* | Full AI Synthesis + Agent Swarm *(Soon)* |
| **24/7 Live Radar Streams & 20.8k Audits Archive** | GitHub Radar | 5 Streams + Archive | All 6 Streams + ZK | All 6 Streams + Instant Alerts |
| **JSON export** | — | Summary | Full technical | Full |

> 👁️ **GUEST** — entry map. See the surface.  
> 🟥 **RADAR** — pressure map. Understand the risk structure + 12 intelligence engines.  
> 📋 **RAW** — data map. Pure technical dump, ZK Groth16 math, and Matrix Sandbox v16.2.  
> 🔥 **BLACKBOX** — consequence map. Exploit paths, drift, unredacted intelligence stack.

---

## Quick Start

1. **Web Terminal:** Open **[https://black-oracle.com](https://black-oracle.com)** — run an instant scan on the homepage or sign in to `/dashboard` to access all 14 intelligence tools, 6 live radar streams, and 20,826 archived dossiers.
2. **Telegram Bot:** Open **[@BlackOracleBORIS_bot](https://t.me/BlackOracleBORIS_bot)** — drop a contract address, GitHub repo URL, or token ticker, and sync your Telegram history with the Web Terminal in 1 click.

**Accepted inputs:**
- `owner/repo` or `https://github.com/...` — GitHub repository
- `0x...` — EVM contract address
- `C...` or `CODE:ISSUER` — Soroban contract / Stellar asset
- Explorer URLs (Etherscan, BscScan, Arbiscan, BaseScan, PolygonScan, etc.)
- `TOKEN` — ticker (market + derivatives scan)

No setup. No external API keys required.

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

## Links

| | |
|---|---|
| 🌐 **Web Terminal** | [https://black-oracle.com](https://black-oracle.com) |
| 🤖 **Telegram Bot** | [@BlackOracleBORIS_bot](https://t.me/BlackOracleBORIS_bot) |
| 💬 **Support / Architect** | [@V_swarm](https://t.me/V_swarm) |
| 🐦 **Twitter/X** | [@BlackOracleRoot](https://x.com/BlackOracleRoot) |

---

<div align="center">

*Not investment advice. Not a guarantee. Not "scam / not scam".*

**BORIS shows where the lever is.**

</div>
