# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Dot-Ring Application](https://github.com/Chainscore/posg-apply/blob/master/applications/dot-ring.md)
* **Milestone Number:** 2
* **DOT Payment Address:** `1iP4qFqt7SRtditzaDBodiwWePpQdUhWGf3bXgL5WYN96hV`

**Context** (optional)

This milestone marks the completion of the DotRing development. It includes the final published library, developer documentation, performance optimizations, and the official PyPI package release. Additionally, this delivery includes the submission of a research paper to IEEE and articles explaining the grant's work.

**Deliverables**


| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | [LICENSE](https://github.com/Chainscore/dot-ring/blob/main/LICENSE) | MIT License | 
| 0b. | Documentation | [Docs](https://dotring.chainscore.finance/) | Developer documentation including API reference and tutorials. |
| 0c. | Testing and Testing Guide | [TESTING.md](https://github.com/Chainscore/dot-ring/blob/master/TESTING.md) | Full test suite coverage including property-based tests and integration tests. |
| 0d. | Docker | [Dockerfile](https://github.com/Chainscore/dot-ring/blob/master/Dockerfile) | Updated container setup for testing and usage. |
| 0e. | Article | [Article 1](https://chainscore.finance/en/blog/from-bytes-to-points-how-try-and-increment-and-elligator-2-map-to-curves) [Article 2](https://chainscore.finance/blog/verifiable-randomness-with-context-understanding-vrf-with-additional-data-vrf-ad) [Article 3](https://chainscore.finance/en/blog/understanding-elliptic-curves-in-cryptography) | Article/Workshop explaining the grant achievements. |
| 0f. | Research Papers | [Papers/](https://ieeexplore.ieee.org/document/11158167) | Research paper submitted to IEEE. |
| 1. | Performance Optimization | [Benchmarks](https://github.com/Chainscore/dot-ring/blob/main/docs/BENCHMARK.md) | Optimized implementations by using blst for MSM and pairing which uses low level C and assembly code. |
| 2. | PyPI Release | [PyPI Link](https://pypi.org/project/dot-ring/) | The library is packaged and released on PyPI. |
| 3. | Final Source Code | [Source](https://github.com/Chainscore/dot-ring/tree/master) | Final version of the library with refined APIs and full feature set. |

**Additional Information**
> Any further comments on the milestone that you would like to share with us.

**Key Achievements**
1. **PyPI Release**: Successfully published the `dot-ring` package to the Python Package Index.
2. **Research Contribution**: Completed a research paper advancing the field of Ring VRFs and Bandersnatch crypto.
3. **Performance**: Significant performance improvements in curve arithmetic and proof generation, comparable with the ark-vrf rust implementation.
4. **Developer Docs**: Full developer documentation generated for the entire API, with examples and explainations.

**Instructions for Reviewers**
- To run tests: `uv run pytest tests/`
- To verifying PyPI package: `pip install dot-ring`
