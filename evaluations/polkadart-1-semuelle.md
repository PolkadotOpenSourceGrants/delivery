# Evaluation

- **Status:** In Progress
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadart.md
- **Milestone:** 1

| Deliverable | Accepted | Link | Evaluation Notes |
| ----------- | -------- | ---- |----------------- |
| **0a. License** |<ul><li>[x] </li></ul>| [LICENSE](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/LICENSE) | Apache 2.0 |
| **0b. Documentation** |<ul><li>[x] </li></ul>| [polkadart.dev](https://polkadart.dev/introduction) | — |
| **0c. Testing** |<ul><li>[ ] </li></ul>| [substrate_metadata](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata/test), [polkadart](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart/test), [polkadart_cli](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart_cli/test) | Unit tests will be created for all main functionalities, they can be easily run by running the docker image bellow |
| **0d. Docker** |<ul><li>[x] </li></ul>| [Dockerfile](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/Dockerfile) | see [General Notes](#general-notes) |
| **0e. Article** |<ul><li>[x] </li></ul>| [hackmd.io](https://hackmd.io/@leonardocustodio/polkadart-typed-metadata) | "Polkadart's Typed Metadata" |
| **1. Substrate Metadata** |<ul><li>[ ] </li></ul>| [packages/substrate_metadata](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata) | Typed metadata as default |
| **2. Registry** |<ul><li>[ ] </li></ul>| [packages/substrate_metadata](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata/lib/registry/metadata_type_registry.dart) | — |
| **3. Polkadart CLI** |<ul><li>[ ] </li></ul>| [packages/polkadart_cli](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart_cli) | — |
| **4. Polkadart** |<ul><li>[ ] </li></ul>| [packages/polkadart](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart) | v1.0.0, see also https://pub.dev/packages/polkadart |


## General Notes

### Testing output

```zsh

```