# BORIS — Changelog
![Detectors](https://img.shields.io/badge/ZK_detectors-26-red)
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
## patch 1.3.1 — 2025-03

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
Последнее — обновить README секцию Docs
Найди старую секцию Docs и замени:

markdown

## Docs

- [`docs/architecture.md`](docs/architecture.md) — system architecture + data flow
- [`docs/signals.md`](docs/signals.md) — complete signal reference with weights
- [`docs/tiers.md`](docs/tiers.md) — tier breakdown and examples
- [`CHANGELOG.md`](CHANGELOG.md) — version history

## Example Reports

| Module | Example | Key finding |
|--------|---------|-------------|
| 🔥 BLACKBOX | [Governance Protocol](examples/full-report/sample-governance-protocol.md) | Flash-loan governance · 48 findings outside audit scope |
| 🌐 Soroban Radar | [Stellar Scam Scan](examples/soroban-radar/stellar-scam-scan.md) | 52 scams · $0 oracle cost · 2 factory networks |
| 💰 Funds Flow | [Pool Analysis](examples/funds-flow/sample-pool-analysis.md) | Wash trading 85/100 · 13 signals |
| 📊 Market Engine | [Market Scan](examples/market-scan/sample-market-engine.md) | OI/Depth 26x squeeze · GitHub 444d abandoned |
| 🐋 Holders | [Holder Distribution](examples/holders/sample-holders-analysis.md) | 59.45% single contract · governance capture threshold |
| 🛰 Social | [Social Intelligence](examples/social/sample-social-intelligence.md) | 5 impersonators · 1.0% TG engagement |
