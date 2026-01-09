# Evaluation

- **Status:** In Progress
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadart.md
- **Milestone:** 1

| Deliverable | Accepted | Link | Evaluation Notes |
| ----------- | -------- | ---- |----------------- |
| **0a. License** |<ul><li>[x] </li></ul>| [LICENSE](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/LICENSE) | Apache 2.0 |
| **0b. Documentation** |<ul><li>[x] </li></ul>| [polkadart.dev](https://polkadart.dev/introduction) | — |
| **0c. Testing** |<ul><li>[ ] </li></ul>| [substrate_metadata](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata/test), [polkadart](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart/test), [polkadart_cli](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart_cli/test) | Unit tests will be created for all main functionalities, they can be easily run by running the docker image bellow |
| **0d. Docker** |<ul><li>[ ] </li></ul>| [Dockerfile](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/Dockerfile) | A Dockerfile is provided to run all unit tests without the need of installing any dependencies |
| **0e. Article** |<ul><li>[ ] </li></ul>| [hackmd.io](https://hackmd.io/@leonardocustodio/polkadart-typed-metadata) | We will create an article that will be posted at Medium and Polkadot Forum to explain the new features |
| **1. Substrate Metadata** |<ul><li>[ ] </li></ul>| [packages/substrate_metadata](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata) | Parse and interpretate metadata v16 making it backwards compability with previous versions |
| **2. Registry** |<ul><li>[ ] </li></ul>| [packages/substrate_metadata](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata/lib/registry/metadata_type_registry.dart) | Use the new transaction format v5 to generate extrinsics and keep v4 as fallback  |
| **3. Polkadart CLI** |<ul><li>[ ] </li></ul>| [packages/polkadart_cli](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart_cli) | — |
| **4. Polkadart** |<ul><li>[ ] </li></ul>| [packages/polkadart](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart) | — |


## General Notes

