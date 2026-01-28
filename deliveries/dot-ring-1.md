# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:**[Dot-Ring Application](https://github.com/Chainscore/posg-apply/blob/master/applications/dot-ring.md) 

* **Milestone Number:** 1
* **DOT Payment Address:** `1iP4qFqt7SRtditzaDBodiwWePpQdUhWGf3bXgL5WYN96hV`

**Context**

This milestone delivers the Major Functional components of the DotRing Suite, focusing on implementing the Bandersnatch curve with optimizations, core VRF 
logic (IETF, Pedersen, Ring Proof and Ring VRF), KZG Commitment scheme and the Fiat-Shamir transcript module. It also provides a comprehensive RFC 9380-compliant
hash-to-curve functionality for multiple elliptic curves, supporting both RO (Random Oracle) and NU (Non-Uniform) variants
across Weierstrass, Montgomery, and Twisted Edwards curve families.

**Deliverables**

| Number | Deliverable                | Link                                                                                                                                                   | Notes                                                                                                                                                                                                                                                                                               |
|--------|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0a.    | License                    | [LICENSE](https://github.com/Chainscore/dot-ring/blob/m1_delivery/LICENSE)                                                                             | MIT License                                                                                                                                                                                                                                                                                         |
| 0b.    | Documentation              | [README.md](https://github.com/Chainscore/dot-ring/blob/m1_delivery/README.md)                                                                         | Comprehensive documentation with inline code documentation, and usage examples for IETF VRF, Pedersen VRF, and Ring VRF. Extended documentation with Sphinx will be provided in the final delivery milestone, as covering additional curves for Ring and other VRFs may require structural changes. |
| 0c.    | Testing and Testing Guide  | [TESTING.md](https://github.com/Chainscore/dot-ring/blob/m1_delivery/TESTING.md), [tests/](https://github.com/Chainscore/dot-ring/tree/m1_delivery/tests) | Comprehensive unit tests with IETF test vectors for H2C (RFC 9380) and VRF implementations. Test coverage >80% for core functions                                                                                                                                                                   |
| 0d.    | Docker                     | [Dockerfile](https://github.com/Chainscore/dot-ring/blob/m1_delivery/Dockerfile)                                                                        | Container setup with all dependencies, and test execution.                                                                                                                                                                                                                                          |
| 1.1    | Bandersnatch Curve Implementation | [dot_ring/curve/specs/bandersnatch.py](https://github.com/Chainscore/dot-ring/blob/m1_delivery/dot_ring/curve/specs/bandersnatch.py)                   | Complete Bandersnatch curve arithmetic with GLV endomorphism optimization, achieving ~40% faster scalar multiplication.                                                                                                                                                                             |
| 1.2    | Curve Families & Core Arithmetic | [dot_ring/curve/](https://github.com/Chainscore/dot-ring/tree/m1_delivery/dot_ring/curve)                                                              | Finite field operations, point addition, scalar multiplication, curve-specific optimizations and hash2curve implementation for all curve families                                                                                                                                                   |
| 1.3    | All Curves                 | [dot_ring/curve/specs/](https://github.com/Chainscore/dot-ring/tree/m1_delivery/dot_ring/curve/specs)                                                  | Specification of curves: Bandersnatch, P-256, P-384, P-521, secp256k1, Ed25519, Ed448, Curve25519, Curve448, BLS12-381 G1&G2, JubJub, BabyJubJub                                                                                                                                                    |
| 1.4    | Hash-to-Curve Suites       | [tests/test_h2c_suites/](https://github.com/Chainscore/dot-ring/tree/m1_delivery/tests/test_h2c_suites)                                                | All suites implemented and tested with RFC9380 vectors: RO and NU variants covering Edwards, Weierstrass and Montgomery Curves                                                                                                                                                                      |
| 2.1    | IETF VRF Implementation    | [dot_ring/vrf/ietf/ietf](https://github.com/Chainscore/dot-ring/blob/m1_delivery/dot_ring/vrf/ietf)                                                    | Full IETF ECVRF implementation (RFC 9381) with KeyGen, Prove, Verify operations                                                                                                                                                                                                                     |
| 2.2    | IETF VRF Tests             | [test_vrfs/test_ietf](https://github.com/Chainscore/dot-ring/tree/m1_delivery/tests/test_vrfs/test_ietf)                                               | Comprehensive tests with IETF test vectors for Bandersnatch, P-256, P-384, secp256k1 curves                                                                                                                                                                                                         |
| 3.1    | Pedersen VRF Implementation | [dot_ring/vrf/ietf/pedersen](https://github.com/Chainscore/dot-ring/tree/m1_delivery/dot_ring/vrf/pedersen)                                            | Pedersen VRF with privacy-preserving properties (public key not exposed)                                                                                                                                                                                                                            |
| 3.2    | Pedersen VRF Tests         | [test_vrfs/test_pedersen](https://github.com/Chainscore/dot-ring/tree/m1_delivery/tests/test_vrfs/test_pedersen)                                       | Comprehensive tests with Pedersen test vectors for Bandersnatch, P-256, P-384, secp256k1 curves                                                                                                                                                                                                     |
| 4.1    | Ring Proof Implementation  | [dot_ring/ring_proof](https://github.com/Chainscore/dot-ring/tree/m1_delivery/dot_ring/ring_proof)                                                     | A Complete Ring Proof Implementation with KZG, Fiat-Shamir Transcript for generating ZK-Proofs                                                                                                                                                                                                      |
| 4.2    | Ring proof Tests           | [test_vrfs/test_ring_proof](https://github.com/Chainscore/dot-ring/tree/m1_delivery/tests/test_vrfs/test_ring_proof)                                   | Comprehensive tests with Ring Proof test vectors for Bandersnatch                                                                                                                                                                                                                                   |
| 5.1    | Ring VRF Implementation    | [vrf/ring/](https://github.com/Chainscore/dot-ring/tree/m1_delivery/dot_ring/vrf/ring)                                                                 | Full Ring VRF Implementation (Utilizing Pedersen + Ring Proof)                                                                                                                                                                                                                                      |
| 5.2    | Ring VRF Tests             | [tests/test_h2c_suites/](https://github.com/Chainscore/dot-ring/tree/m1_delivery/tests/test_vrfs/test_ring_vrf)                                        | Comprehensive tests with Ring VRF test vectors for Bandersnatch                                                                                                                                                                                                                                     |

**Additional Information**

**Key Achievements**

1. **RFC 9380 Compliance**: Full implementation of hash-to-curve for all the curves with both RO and NU variants
2. **Performance Optimization**: GLV-accelerated Bandersnatch achieving ~40% faster scalar multiplication
3. **Comprehensive Testing**: 100% pass rate on RFC9380 hash-to-curve suites,and All VRF implementations
4. **Multi-Curve Support**: Unified API supporting Weierstrass, Montgomery, and Twisted Edwards curve families
5. **Security**: Constant-time implementations avoiding timing side-channels (Excluding Try-And-Increment)
6. Published a Research paper on [IEEE Xplore](https://ieeexplore.ieee.org/document/11158167)

**Architecture Highlights**

- **Modular Design**: Separation of concerns with dedicated modules
- **RFC Compliance**: Strict adherence to RFC 9380 (hash-to-curve) and RFC 9381 (VRF) specifications
- **Extensibility**: Easy to add new curves and VRF variants
- **Cross-Verification**: Compatible with Rust ark-vrf implementation for cross-checking

**Next Steps (Milestone 2)**

- Extending the VRF Implementation to support more curves
- Performance optimization and benchmarking
- PyPI package release