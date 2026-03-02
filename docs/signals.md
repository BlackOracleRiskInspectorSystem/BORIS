# BORIS — Signal Reference

Complete list of signals across all layers with weights and detection logic.

---

## Static Code Signals

| Signal | Severity | Description | Detection |
|--------|----------|-------------|-----------|
| `NO_SNAPSHOT` | CRITICAL | Voting uses current balance, no checkpoint | Missing ERC20Snapshot or block-based checkpoint in vote functions |
| `ARBITRARY_CALL` | CRITICAL | Contract executes arbitrary external calls | `call()` / `delegatecall()` to user-controlled address |
| `REENTRANCY` | CRITICAL | State updated after external call | CEI pattern violation detection |
| `DELEGATECALL_MISUSE` | CRITICAL | Delegatecall to untrusted target | Delegatecall where target is not hardcoded |
| `EMERGENCY_DRAIN` | CRITICAL | Function can drain all funds | `withdraw(address, amount)` without timelock in privileged context |
| `HIDDEN_BACKDOOR` | CRITICAL | Obfuscated control function | Encoded function selectors, hidden admin paths |
| `UNCHECKED_TRANSFER` | HIGH | Return value of transfer not checked | Missing require on ERC20 transfer return |
| `AMM_SPOT_ORACLE` | HIGH | Spot AMM price used as oracle | `getReserves()` or `slot0()` used in price-sensitive logic |
| `HIDDEN_MINT_FUNCTION` | HIGH | Mint without Transfer event or bounds | Internal mint bypassing standard event emission |
| `CENTRALIZED_CONTROL` | HIGH | Critical function behind single key | `onlyOwner` on pause/upgrade/drain without timelock |
| `OFFCHAIN_SIGNATURE_RISK` | HIGH | Signature replay / misuse risk | `ecrecover` without domain separator or nonce |
| `TX_ORIGIN_AUTH` | HIGH | `tx.origin` used for authorization | `require(tx.origin == owner)` pattern |
| `ACCESS_CONTROL_MISCONFIG` | HIGH | Sensitive function without access control | Public/external state-changing function with no modifier |
| `PROXY_UPGRADE_SURFACE` | HIGH | Upgradeable proxy without timelock | UUPS/Transparent proxy with unprotected `upgradeTo` |
| `STORAGE_COLLISION` | HIGH | Proxy storage overlaps with implementation | Storage slot analysis across proxy/impl pair |
| `FLASH_LOAN_GOVERNANCE` | MEDIUM | Governance capturable via flash loan | Combines NO_SNAPSHOT + liquid market |
| `PRIVILEGED_ROLE_ESCALATION` | MEDIUM | Role can grant itself higher role | `grantRole(ADMIN_ROLE, msg.sender)` without guard |

---

## Onchain Signals

| Signal | Severity | Description |
|--------|----------|-------------|
| `PROXY_NO_IMPL` | HIGH | Proxy implementation unknown or unverified |
| `NOT_VERIFIED` | MEDIUM | Contract source not verified on explorer |
| `UNVERIFIED_WITH_BALANCE` | HIGH | Unverified contract holds significant funds |
| `CUSTOM_PROXY_PATTERN` | MEDIUM | Non-standard proxy pattern detected |
| `ROLE_CONCENTRATION` | HIGH | Single address controls multiple privileged roles |
| `ADMIN_SURFACE_WIDE` | MEDIUM | Large number of privileged functions exposed |

---

## Market Signals

| Signal | Weight | Description | Threshold |
|--------|--------|-------------|-----------|
| `THIN_BOOK_HIGH_OI` | +18 | OI/Depth ratio indicates squeeze risk | OI/Depth > 10x |
| `OI_VELOCITY_SURGE` | +15 | OI accumulating faster than baseline | Velocity > 2x baseline |
| `OI_PRICE_DIVERGENCE` | +12 | OI rising while price falling (or inverse) | Divergence > 20% |
| `FUNDING_EXTREME` | +10 | Funding rate at extreme level | |abs(funding)| > 0.05% |
| `SMART_MONEY_LONG` | +6 | Top traders significantly more long than retail | Divergence > 15% |
| `SMART_MONEY_SHORT` | +8 | Top traders significantly more short than retail | Divergence > 15% |
| `SUPPLY_MODERATE_CIRC` | +6 | Less than 60% of supply circulating | Circ < 60% |
| `SUPPLY_LOW_CIRC` | +12 | Less than 30% of supply circulating | Circ < 30% |
| `GITHUB_ABANDONED` | +20 | No development activity | Last push > 365 days |
| `GITHUB_SLOWING` | +10 | Reduced development activity | Last push > 90 days |
| `WASH_VOLUME` | +15 | Volume appears inflated via wash trading | Pool manipulation score > 70 |
| `LIQUIDATION_CASCADE_RISK` | +14 | Large liquidation cluster near current price | Cluster > 5% of OI within 3% price |
| `CROSS_EXCHANGE_OI_DIVERGENCE` | +8 | OI distribution heavily skewed to one exchange | Single exchange > 80% of total OI |

---

## Holder Signals

| Signal | Severity | Description | Threshold |
|--------|----------|-------------|-----------|
| `EXTREME_CONCENTRATION` | CRITICAL | Top-10 real > 85% | Real Top-10 > 85% |
| `HIGH_CONCENTRATION` | HIGH | Top-10 real 70–85% | Real Top-10 70–85% |
| `SINGLE_DOMINANT_HOLDER` | HIGH | One address > 30% | Single holder > 30% |
| `GOVERNANCE_CONCENTRATION` | HIGH | Whale holdings enable governance capture | Whale % vs governance quorum |
| `CONTRACT_DOMINANT` | MEDIUM | Most supply in contracts (not wallets) | Contract holders > 80% of Top-10 |

---

## Social Signals

| Signal | Severity | Description | Threshold |
|--------|----------|-------------|-----------|
| `FAKE_FOLLOWERS` | HIGH | High follower count, dead engagement | Followers > 5K, no recent activity |
| `ARTIFICIAL_ENGAGEMENT` | MEDIUM | View ratio below threshold | View ratio < 10% for large accounts |
| `IMPERSONATOR_DETECTED` | HIGH | Clone channel found | Levenshtein distance ≤ 2 from official |
| `CROSS_PLATFORM_MISMATCH` | MEDIUM | Extreme follower disparity across platforms | Ratio > 100x between platforms |
| `HOLLOW_COMMUNITY` | MEDIUM | Large group, minimal reactions | < 1% view ratio on group |
| `DEAD_CHANNEL_CLUSTER` | LOW | Multiple dead satellite channels | 3+ dead channels with >1K followers |
| `SUSPECT_VIEW_RATIO` | MEDIUM | Views exceed or nearly exceed subscribers | View ratio > 95% |
| `CONTENT_SCAM_PATTERN` | CRITICAL | Scam/shill language in posts | Keyword pattern matching |

---

## Funds Flow Signals

| Signal | Severity | Description | Confidence |
|--------|----------|-------------|------------|
| `WASH_TRADING` | CRITICAL/HIGH | Cyclic flow between same addresses | 85% |
| `BOT_PATTERN` | MEDIUM | High-frequency mechanical trading | 35% |
| `WHALE_ACCUMULATION` | LOW | Single actor dominates pool activity | 35% |
| `FUND_EXTRACTION` | HIGH | One-directional large outflow to unknown | 70% |
| `CEX_CONSOLIDATION` | INFO | Funds flowing to known CEX address | 90% |
| `SYBIL_CLUSTER` | HIGH | Multiple addresses acting as one | 65% |

---

## Audit Drift Signals

| Signal | Severity | Description |
|--------|----------|-------------|
| `STALE_AUDIT` | HIGH | Last audit > 365 days ago |
| `CRITICAL_DRIFT` | CRITICAL | New critical findings since last audit |
| `SEVERITY_ESCALATION` | HIGH | Overall severity higher than at audit time |
| `NEW_EXECUTION_SURFACE` | HIGH | New privileged functions since audit |
| `UNAUDITED_HIGH_RISK_FILE` | HIGH | File with critical findings not in audit scope |
| `GOVERNANCE_MUTATION` | HIGH | Governance logic changed since audit |

---

## Composite Scoring
Structural Profile (0–100 each):
Governance Risk Index    = f(critical_findings, governance_patterns, role_density)
Liquidity Risk Index     = f(pool_depth, manipulation_score, oracle_dependency)
Holder Concentration     = f(real_top10, single_dominant, governance_threshold)
Code Pattern Density     = f(finding_count, severity_distribution, archetype_adj)
Social Trust             = f(engagement_quality, impersonators, platform_consistency)
Behavioral Risk          = f(manipulation_score, governance_mismatch, new_findings)

Overall Risk Score = weighted combination of all indices
Exploit Chain Score = prerequisite_match × liquidity_feasibility × confidence



---

## Archetype Normalization Table

| Pattern | Default Severity | After Normalization (DEX) | After Normalization (Stablecoin) | After Normalization (DAO) |
|---------|-----------------|--------------------------|----------------------------------|---------------------------|
| `mint()` unlimited | CRITICAL | INFO (by design) | INFO (by design) | HIGH (contradiction) |
| `blacklist()` | HIGH | N/A | INFO (by design) | CRITICAL (contradiction) |
| `pause()` | HIGH | MEDIUM | INFO (by design) | HIGH (contradiction) |
| LP burn function | HIGH | INFO (by design) | N/A | MEDIUM |
| Proposal execution | HIGH | N/A | N/A | INFO (by design) |
| `emergencyWithdraw` | CRITICAL | MEDIUM | MEDIUM | CRITICAL (contradiction) |
