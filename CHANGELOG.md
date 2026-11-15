# BORIS — Changelog

![Version](https://img.shields.io/badge/version-Beta_v1.4-e11d48)
![Modules](https://img.shields.io/badge/modules-335%2B-blue)
![Detectors](https://img.shields.io/badge/ZK_detectors-26-red)

## beta 1.4 — 2026-11

### Added
- **Full Web SaaS Terminal (`https://black-oracle.com`)** synchronized with `@BlackOracleBORIS_bot`:
  - **14 Interactive Intelligence Engines** in Operator Cabinet (`/dashboard`):
    1. Holders & Whales Analyzer
    2. Market & Derivatives Terminal (`/market`)
    3. 14-Day Funds Flow Graph Analyzer
    4. Social & OSINT Cross-Scanner
    5. Soroban / Stellar SIM Inspector
    6. **OSPEC Secret & Config Intelligence** (`1,144,698` findings across `31,837` repos, L2.5-filtered to `7,087` verified `REAL` secrets and `550` `LIVE` keys with repository drill-down)
    7. **2,539 Historical Exploits & Foundry PoC Corpus** (`1,678` full technical writeups with Foundry tests + `861` DeFiHackLabs incidents)
    8. **Deployer & Address Profiler** (`AddressIntelligence` + batch `DeployAnalyzer` creator wallet forensics)
    9. **Proxy & EIP-1967 Storage Slot Inspector** (`implementation`, `admin`, `beacon`, legacy OZ slots + uninitialized `initialize()` probe)
    10. **Flash-Loan & Spot-Oracle Detector** (`slot0`/`getReserves` vs TWAP/Chainlink + bridge bytecode signatures)
    11. **Web3 Surface Mapper** (18-subdomain parallel recon + JS bundle contract/RPC/sourcemap extraction)
    12. **Post-Audit Git Drift Analyzer** (automated PDF audit parsing + Git commit delta since last audit)
    13. **ZK Groth16 Verifier Auditor** (BN254 curve/subgroup check + lookup against `4,982` on-chain verifiers)
    14. **Matrix Sandbox v16.2** (`sys.addaudithook` kernel-level isolated execution with `BLOCKED / SIMULATED / EXECUTED` telemetry)
  - **6 Live 24/7 Radar Streams** with server-side pagination (`289,000+` indexed targets + `10,826` pre-computed dossiers in `AUDITS_BASE` + 1-click DeFiLlama Enricher).
  - **Sovereign Multi-Chain Checkout (`hd_treasury.py`):** BIP-44 HD wallet invoicing across 7 networks (`Arbitrum`, `Base`, `BSC`, `Polygon`, `Ethereum`, `TRON`, `Solana`) + `@CryptoBot` + 1-click Telegram account/history sync (`websync_`).
- **BORIS Neural Cortex (`Powered by AI — Rolling Out`):**
  - Two-stage neuro-symbolic architecture: deterministic 19-layer engine produces a verified JSON dossier first, followed by AI interpretation grounded in 10,826 archived audits and 2,539 exploit precedents (0% raw-code hallucination).
- **OSPEC L2.5 Verification & Context Gating Upgrade:**
  - `l2_validators_v2`, `l2_coverage`, `kind_rules`, and `secret_signatures` expanded with 63 automated self-tests (`test_ospec.py`).
  - `api_key_pool.py` upgraded to rotate 100+ RPC/API keys (`49` Alchemy, `35` Infura, `6` Etherscan V2, `3` GitHub PAT, `3` Ankr, `2` Helius, `2` CoinGecko).

---

## patch 1.3.2 — 2026-03

### Added
- ZK Intelligence Engine v3.0 [PREVIEW]
  - 26 detectors, 55+ vulnerability classes
  - VK soundness (gamma==delta), curve math, protocol logic, signal binding
  - Proof forgery detection (frozen heart, malleability, negation)
  - Backdoor detection (8 patterns + kill switch)
  - Bytecode VK extraction (PUSH32/PUSH16+SHL) — no source required
  - External verifier mutable pointer detection
  - Trusted Setup Forensics — entropy, generator reuse, ceremony detection
  - VK fingerprinting + clone detection + archetype engine (5 classes)
  - ZK Radar — cross-chain verifier discovery + cluster analysis
  - Severity calibration — archetype-aware design tradeoff remapping
  - Validated: Tornado Cash (ETH/BSC/Polygon/DAI), FoomCash, Aztec Connect, Polygon zkEVM, zkSync Era

---

## patch 1.3.1 — 2026-03

### Added
- Vyper language support — full static analysis + Invariant Correlation Engine integration (11 languages total)
- CoinGecko social metrics database integration

### Improved
- Invariant Correlation Engine — stronger chain building, higher precision linking
- Radar detection cycle — stabilized, faster catches, cleaner filtering
- Social Intelligence (Telegram + X) — search and parsing logic completely rebuilt
- BLACKBOX report visualization — cleaner structure, clearer verdicts
- Search speed optimized across all modules
- Bot trimmed — removed excess, kept what works

### Fixed
- Deployment pipeline issues
- Minor text corrections across reports

---

## beta 1.3 — 2026-03-02

### Added
- Soroban Intelligence Module (SIM) — full Stellar/Soroban asset analysis
  - Oracle manipulation cost calculator (YieldBlox-class detection)
  - Scam factory detection and batch analysis
  - Continuous Radar for Stellar ecosystem (358+ assets monitored)
  - SDEX orderbook microstructure analysis
  - Price impact curve visualization
- Social Scanner v2.0
  - Impersonation detection via Levenshtein + character substitution
  - Cross-platform consistency scoring
  - View ratio analysis (hollow community detection)
  - Suspect engagement classification
- Funds Flow Analyzer — pool-specific analysis mode
  - HTML explorer fallback when API unavailable
  - Actor dominance scoring
- Market Detection Engine — temporal tracking
  - Multi-scan persistence analysis
  - Chronic signal detection across scan history
  - Regime classification (MIXED / BULLISH / BEARISH / SQUEEZE)
- Holders Analyzer
  - CEX/LP/burn correction for real concentration
  - Governance concentration heuristics
  - Proxy holder detection

### Improved
- Archetype normalization: reduced false positives by ~13%
- Exploit chain scoring: added amplifier context (liquidity, holder concentration, audit age)
- Audit drift: now tracks prerequisite drift in addition to severity drift
- Cross-layer correlation: social signals now feed into behavioral risk score

### Fixed
- Proxy resolution: custom proxy patterns (ProtectedTransparentProxy, ProtectedPublicBeaconProxy)
- BSC token transfer API fallback to HTML explorer
- Stellar Horizon 400 error handling in asset analysis

---

## beta 1.2 — 2026-03

### Added
- Audit drift analysis — PDF parsing + git diff from audit commit
- Attack Simulation Correlation — attacker mock detection
- Deployment graph awareness — multi-chain contract mapping
- DeFiLlama Radar — continuous new protocol monitoring
- Verified Contract Radar — EVM new contract monitoring

### Improved
- GitHub Radar: scoring expanded to 20+ signals
- Static analysis: added TON (FunC/Tact/Fift) language support
- Onchain: Stellar/Soroban chain support added

---

## beta 1.1 — 2026-03

### Added
- Cross-layer correlation engine
- Trust model extraction
- ABI surface intelligence
- Behavioral layer (cyclic swap detection, wash trading)
- Derivatives analysis module (Binance · Bybit · OKX)

### Improved
- EVM chain support expanded: Base, Optimism added
- Holder analyzer: Solana support via Helius API
- Social scanner: Discord analysis added

---

## beta 1.0 — 2026-03

### Initial release
- Static code analysis (Solidity, Rust, Move, Go, Python, TypeScript)
- Slither + Aderyn + Semgrep integration
- Basic onchain structural analysis (EVM)
- Proxy resolution (ERC1967, UUPS, Transparent)
- Governance & privilege intelligence
- GitHub Radar (initial version)
- Telegram bot with 4 tiers (GUEST · RADAR · RAW · BLACKBOX)
- CryptoBot payment integration
