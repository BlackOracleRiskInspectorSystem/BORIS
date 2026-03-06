markdown

# ZK Verifier — Clean Pass

> BORIS ZK Intelligence Engine · On-chain audit
> Target: `0xFF1F2B4ADb9dF6FC8eAFecDcbF96A2B351680455` · Ethereum

## Result
✓ No issues



No Groth16 soundness violations. No backdoors. No mutable verifier.
Clean verifier — properly configured trusted setup.
examples/zk-verifier/sample-tornado-calibrated.md
markdown

# ZK Verifier — Tornado Cash (Calibrated Findings)

> BORIS ZK Intelligence Engine · On-chain audit
> Target: `0x12D66f87A04A9E220743712cE6d9bB1B5616B8Fc` · Ethereum
> Tornado Cash 0.1 ETH pool

## Summary

| Severity | Count |
|----------|-------|
| 🔴 CRITICAL | 0 |
| 🟠 HIGH | 3 |
| ℹ️ INFO | 11 |
| **Total** | **14** |

## Key Findings

### 🟠 HIGH — ZK_BACKDOOR_ACCESS_CONTROL
File: :191 | Confidence: 95%
Access control on verifyProof.
Evidence: matched: onlyOperator
→ Remove non-crypto logic from verifyProof.



### 🟠 HIGH — ZK_MUTABLE_VERIFIER_CRITICAL
File: :189 | Confidence: 90%
Verifier address (verifier) is not immutable/constant.
Admin/operator can replace with broken verifier (gamma==delta) and drain all funds.
Evidence: variable: verifier | mutable: True
→ Make verifier immutable or add timelock + governance.



### 🟠 HIGH — ZK_PROOF_ELEMENT_UNCHECKED
Confidence: 75%
Frozen Heart: proof.A (G1) identity, proof.B (G2) identity,
proof.C (G1) identity not validated. Ref: Trail of Bits 2022.
→ Check proof elements != identity and in correct subgroup.



## Design Tradeoffs (severity calibrated)

All originally HIGH, remapped to INFO based on TORNADO_MIXER archetype:

| Finding | Tradeoff |
|---------|----------|
| ZK_FRONTRUN_NO_RECIPIENT_IN_PROOF | Privacy vs frontrun risk |
| ZK_UPGRADABLE_VERIFIER | Admin trust vs bug-fix capability |
| ZK_FEE_CHANGEABLE_NO_TIMELOCK | Admin agility vs user protection |
| ZK_FRONTRUN_NO_FEE_IN_PROOF | Relayer manipulation vs UX |
| ZK_PROOF_MALLEABILITY | Gas cost vs defense-in-depth |
| ZK_NO_RELAYER_VALIDATION | Censorship resistance vs front-running |

## Intelligence
🔍 CLONE: TORNADO_CLONE_HIGH (100% confidence, score 34/30)
Matched: merkle_tree, denomination, withdraw_func, deposit_func,
commitment_event, withdrawal_event, relayer_param, fee_param,
verifier_call, root_history, hasher, nullifier_check

🏛 ARCHETYPE: TORNADO_MIXER (84% confidence)
Audit checklist: nullifier double-spend, merkle root validation,
frontrun protection, reentrancy, VK soundness

🔀 MULTI-ARCHETYPE: TORNADO_MIXER + SEMAPHORE_IDENTITY

📡 EXTERNAL VERIFIER: verifier.verifyProof() — MUTABLE
VK lives in separate contract — admin can swap at any time



## Calibration Note

> 6 findings remapped from HIGH → INFO based on Tornado Cash architecture.
> Privacy mixers make intentional design tradeoffs.
> BORIS maps the tradeoffs — doesn't penalize them.
> Zero false criticals on a known-good protocol.
examples/zk-verifier/sample-foomcash-critical.md
markdown

# ZK Verifier — FoomCash (CRITICAL: gamma==delta)

> BORIS ZK Intelligence Engine · On-chain audit
> Target: `0xc043865fb4D542E2bc5ed5Ed9A2F0939965671A6` · Ethereum
> FoomCash mixer — $2.26M exploit (March 2025)

## Summary

| Severity | Count |
|----------|-------|
| 🔴 CRITICAL | 2 |
| 🟠 HIGH | 5 |
| ℹ️ INFO | 5 |
| **Total** | **12** |

## 🔴 CRITICAL Findings

### ZK_GAMMA_DELTA_COLLISION
File: :36 | Confidence: 100%

FATAL: gamma2 == delta2 == G2 generator — Groth16 soundness broken.
Phase 2 never executed. Anyone can forge proofs.
All funds at immediate risk.

Evidence:
gamma2.x1: 0x198e9393920d483a7260bfb731fb5d25f1aa493335a9e71297e485b7aef312c2
delta2.x1: 0x198e9393920d483a7260bfb731fb5d25f1aa493335a9e71297e485b7aef312c2
(identical — both are BN254 G2 generator)

is_g2_generator: True
exploit_complexity: TRIVIAL
reference: FoomCash $2.26M / Veil Cash — Feb 2025

→ EMERGENCY: Pause. Run Phase 2 ceremony. Redeploy.



### ZK_NO_NULLIFIER_TRACKING
File: :77 | Confidence: 90%

Mixer calls verifier but has no nullifier mapping. Double-spend possible.

Evidence:
has_verify: True
has_nullifier_mapping: False

→ Add mapping(bytes32=>bool) nullifiers.



## 🟠 HIGH Findings

| Finding | Confidence | Detail |
|---------|-----------|--------|
| ZK_IC_VECTOR_POISONING_UNCHECKED | 85% | No input.length vs IC.length validation |
| ZK_SETUP_PARTIAL_GENERATORS | 85% | 2/4 VK points are generators — partial ceremony |
| ZK_FRONTRUN_NO_RECIPIENT_IN_PROOF | 80% | Recipient not in proof — frontrun possible |
| ZK_NO_ROOT_VALIDATION | 75% | No Merkle root validation |
| ZK_PROOF_ELEMENT_UNCHECKED | 75% | Frozen Heart — proof identity not validated |

## VK Profile
Fingerprint:  dacabf98eed875c0
Full SHA256:  dacabf98eed875c0d6b86a3117341f853393dae2eb5794ce3666b9ed39f51576
Public inputs: 7
IC length:    8
Constraints:  10K-50K (medium, mixer-class)
Circuit class: MIXER_CLASS
Setup status: BROKEN_GAMMA_EQ_DELTA

gamma==delta: YES ← FATAL
gamma=G2gen:  YES ← Phase 2 never ran
delta=G2gen:  YES ← Phase 2 never ran



## Attack Chain
gamma2 == delta2 == G2 generator → Groth16 verification equation degenerates → Any (A, B, C) satisfying simplified equation passes
No nullifier tracking → Same proof can be replayed infinitely
No root validation → Fabricated Merkle roots accepted
Result: forge proof → drain all deposits → replay → drain again
Exploit complexity: TRIVIAL



## Context

FoomCash lost $2.26M in March 2025. The verifier was deployed with
Phase 1 setup only — Phase 2 ceremony was never executed, leaving
gamma and delta as the BN254 G2 generator. This collapses Groth16
soundness entirely.

$1.84M rescued by Decurity. $320K retained as protocol bounty.
Net loss: $420K.

BORIS ZK Intelligence Engine detects this pattern automatically
via VK point extraction and generator comparison.
README Example Reports — добавь строки:
markdown

| 🔐 ZK Clean | [Clean Verifier](examples/zk-verifier/sample-clean-pass.md) | ✓ No issues · properly configured setup |
| 🔐 ZK Calibrated | [Tornado Cash](examples/zk-verifier/sample-tornado-calibrated.md) | 14 findings · 6 design tradeoffs · 0 false criticals |
| 🔐 ZK Critical | [FoomCash](examples/zk-verifier/sample-foomcash-critical.md) | gamma==delta · no nullifier · $2.26M exploit |
