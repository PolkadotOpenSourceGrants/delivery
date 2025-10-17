## Evaluation
- **Status:** Changes Requested
- **Application Document:** [`dotring.md`](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/dot-ring.md)
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | ------- | ---- | ---------------- |
| 0a. | License | [x] | `dot-ring/LICENSE` | MIT license present as required. |
| 0b. | Documentation | [x] | `dot-ring/README.md`, `dot-ring/TESTING.md` | Usage, setup, and test instructions documented, matching scope. |
| 0c. | Testing and Testing Guide | [ ] | `dot-ring/tests/`, `dot-ring/TESTING.md` | `python -m pytest --cov=dot_ring --cov-report=term-missing --cov-report=html tests` now passes (39 tests) once `blst` bindings are present, but several core modules are still <80 % coverage (`field_element.py` 76 %, `curve/specs/ed25519.py` 69 %, `sw_affine_point.py` 74 %, `ring_proof/pcs/kzg.py` 70 %), so the testing deliverable remains incomplete. |
| 0d. | Docker | [x] | `dot-ring/Dockerfile` | Dockerfile provisions dependencies (including blst build) and runs pytest with coverage. |
| 1.1 | Bandersnatch Curve Implementation | [x] | `dot-ring/dot_ring/curve/specs/bandersnatch.py` | Implements Bandersnatch parameters with GLV hooks per spec (`BandersnatchCurve`, `BandersnatchPoint`). |
| 1.2 | Curve Families & Core Arithmetic | [ ] | `dot-ring/dot_ring/curve/` | Despite new property-style tests (`tests/test_curve_ops`), foundational components (`field_element.py` 76 %, `sw_affine_point.py` 74 %) remain under the ≥80 % threshold; additional coverage is required. |
| 1.3 | All Curves | [ ] | `dot-ring/dot_ring/curve/specs/` | Curve-specific modules must reach ≥80 % individually; `curve/specs/ed25519.py` is still 69 %. Provide further tests or document exclusions. |
| 1.4 | Hash-to-Curve Suites | [ ] | `dot-ring/tests/test_h2c_suites/` | RFC 9380 vectors execute, yet key support modules for hashing-to-curve (e.g., `sw_affine_point.py`) stay below 80 %; expand tests to cover remaining branches. |
| 2.1 | IETF VRF Implementation | [x] | `dot-ring/dot_ring/vrf/ietf/ietf.py` | Implements keygen/prove/verify per RFC 9381 with ≥97 % coverage. |
| 2.2 | IETF VRF Tests | [x] | `dot-ring/tests/test_vrfs/test_ietf/` | Suite exercises the IETF VRF across supported curves with adequate coverage. |
| 3.1 | Pedersen VRF Implementation | [x] | `dot-ring/dot_ring/vrf/pedersen/pedersen.py` | Pedersen VRF logic covered (>95 %). |
| 3.2 | Pedersen VRF Tests | [x] | `dot-ring/tests/test_vrfs/test_pedersen/` | Pedersen vectors executed with sufficient coverage. |
| 4.1 | Ring Proof Implementation | [ ] | `dot-ring/dot_ring/ring_proof/` | With blst installed, tests cover both native and third-party paths, but `ring_proof/pcs/kzg.py` remains at 70 %; add targeted tests (or guard optional paths) to reach ≥80 %. |
| 4.2 | Ring Proof Tests | [x] | `dot-ring/tests/test_ring_proof/`, `tests/test_ring_vrf_with_third_party_msm.py` | Third-party MSM test passes when blst is available; document the dependency for reviewers. |
| 5.1 | Ring VRF Implementation | [x] | `dot-ring/dot_ring/vrf/ring/ring_vrf.py` | Ring VRF assembly covered (>96 %) and functionally validated. |
| 5.2 | Ring VRF Tests | [x] | `dot-ring/tests/test_vrfs/test_ring_vrf/` | Bandersnatch ring-VRF vectors executed successfully. |

**Additional notes**
- Some modules still below the 80 % bar: `dot_ring/curve/field_element.py`, `dot_ring/curve/specs/ed25519.py`, `dot_ring/curve/short_weierstrass/sw_affine_point.py`, `dot_ring/ring_proof/pcs/kzg.py`. Please increase coverage or justify exclusions.
- The third-party MSM test depends on locally built `blst` bindings. Consider adding an installation helper (e.g., optional extras) or skipping gracefully when the dependency is absent.
- Curve operation sanity tests (`tests/test_curve_ops/*.py`) are a good addition; further property-based or edge-case tests would help close the remaining coverage gaps.
- Once per-module coverage meets ≥80 % and the optional dependency is documented/handled, the outstanding deliverables can be reconsidered for acceptance. I'll ask research team to take a look as well. 
