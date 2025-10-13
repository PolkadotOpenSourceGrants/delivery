## Evaluation
- **Status:** Changes Requested
- **Application Document:** [`dot-ring.md`](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/dot-ring.md)
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | ------- | ---- | ---------------- |
| 0a. | License | [x] | `dot-ring/LICENSE` | MIT license present as required. |
| 0b. | Documentation | [x] | `dot-ring/README.md`, `dot-ring/TESTING.md` | Usage, setup, and test instructions documented, matching scope. |
| 0c. | Testing and Testing Guide | [ ] | `dot-ring/tests/`, `dot-ring/TESTING.md` | Pytest suite runs, but several core modules (e.g., `field_element.py` 68 %, `glv.py` 32 %) fall below the promised ≥80 % coverage, so the testing deliverable is incomplete. |
| 0d. | Docker | [ ] | — | No Dockerfile or container resources delivered; milestone notes defer to future work. |
| 1.1 | Bandersnatch Curve Implementation | [x] | `dot-ring/dot_ring/curve/specs/bandersnatch.py` | Implements Bandersnatch parameters with GLV hooks per spec (`BandersnatchCurve`, `BandersnatchPoint`). |
| 1.2 | Curve Families & Core Arithmetic | [ ] | `dot-ring/dot_ring/curve/` | Coverage for foundational components (`field_element.py` 68 %, `glv.py` 32 %, `montgomery/mg_curve.py` 42 %, `montgomery/mg_affine_point.py` 69 %) is below the 80 % threshold; additional tests are required. |
| 1.3 | All Curves | [ ] | `dot-ring/dot_ring/curve/specs/` | Multiple curve modules remain untested (`baby_jubjub.py` 0 %, `curve25519.py` 65 %, `ed25519.py` 72 %, `twisted_edwards/te_affine_point.py` 73 %), so suite-wide coverage is insufficient. |
| 1.4 | Hash-to-Curve Suites | [ ] | `dot-ring/tests/test_h2c_suites/` | While vectors exist, coverage for key hash-to-curve implementations (e.g., `curve25519.py` 65 %, `curve448.py` 80 %, `montgomery/mg_curve.py` 42 %) falls below 80 %; add tests exercising remaining code paths. |
| 2.1 | IETF VRF Implementation | [x] | `dot-ring/dot_ring/vrf/ietf/ietf.py` | Implements keygen/prove/verify per RFC 9381 with ≥95 % coverage. |
| 2.2 | IETF VRF Tests | [x] | `dot-ring/tests/test_vrfs/test_ietf/` | Test suite exercises the IETF VRF across supported curves with adequate coverage. |
| 3.1 | Pedersen VRF Implementation | [x] | `dot-ring/dot_ring/vrf/pedersen/pedersen.py` | Pedersen VRF logic covered by tests (>80 %). |
| 3.2 | Pedersen VRF Tests | [x] | `dot-ring/tests/test_vrfs/test_pedersen/` | Pedersen vectors executed with sufficient coverage. |
| 4.1 | Ring Proof Implementation | [ ] | `dot-ring/dot_ring/ring_proof/` | Core ring-proof modules remain under-tested (`ring_proof/curve/bandersnatch.py` 56 %, `pcs/kzg.py` 49 %, `helpers.py` 83 %); expand tests to reach ≥80 % for each component. |
| 4.2 | Ring Proof Tests | [ ] | `dot-ring/tests/test_vrfs/test_ring_proof/test_ring_proof.py` | Existing tests do not exercise enough code to push ring-proof modules above 80 % coverage. |
| 5.1 | Ring VRF Implementation | [x] | `dot-ring/dot_ring/vrf/ring/ring_vrf.py` | Ring VRF assembly covered (>95 %) and functionally validated. |
| 5.2 | Ring VRF Tests | [x] | `dot-ring/tests/test_vrfs/test_ring_vrf/` | Bandersnatch ring-VRF vectors executed with adequate coverage. |

**Additional notes**
- Modules listed above remain below 80 % and require additional tests before approval.
- Pytest emits a SyntaxWarning for `dot_ring/curve/point.py` (`is not` vs `!=`). Recommend fixing alongside expanded test coverage.
- Docker deliverable remains outstanding; milestone cannot be fully accepted until both coverage gaps and container artefacts are addressed.
- Test suite appropriateness: RFC 9380 vectors validate hash-to-curve for P-256/384/521, secp256k1, Edwards/Curve25519/448, and BLS12-381 suites; RFC 9381 examples underpin the IETF VRF cases; Pedersen and Ring VRF/proof tests rely on ark-vrf-derived vectors. For modules lacking recognised vectors (e.g., BabyJubJub, KZG), add property-based tests or cross-checks against trusted implementations to bolster confidence beyond line coverage.
