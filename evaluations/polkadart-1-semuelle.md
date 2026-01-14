# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadart.md
- **Milestone:** 1

| Deliverable | Accepted | Link | Evaluation Notes |
| ----------- | -------- | ---- |----------------- |
| **0a. License** |<ul><li>[x] </li></ul>| [LICENSE](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/LICENSE) | Apache 2.0 |
| **0b. Documentation** |<ul><li>[x] </li></ul>| [polkadart.dev](https://polkadart.dev/introduction) | — |
| **0c. Testing** |<ul><li>[ ] </li></ul>| [substrate_metadata](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata/test), [polkadart](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart/test), [polkadart_cli](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart_cli/test) | All tests passed using Docker |
| **0d. Docker** |<ul><li>[x] </li></ul>| [Dockerfile](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/Dockerfile) | see [General Notes](#general-notes) |
| **0e. Article** |<ul><li>[x] </li></ul>| [hackmd.io](https://hackmd.io/@leonardocustodio/polkadart-typed-metadata) | "Polkadart's Typed Metadata" |
| **1. Substrate Metadata** |<ul><li>[ ] </li></ul>| [packages/substrate_metadata](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata) | Typed metadata as default |
| **2. Registry** |<ul><li>[ ] </li></ul>| [packages/substrate_metadata](https://github.com/justkawal/polkadart/blob/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/substrate_metadata/lib/registry/metadata_type_registry.dart) | — |
| **3. Polkadart CLI** |<ul><li>[ ] </li></ul>| [packages/polkadart_cli](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart_cli) | — |
| **4. Polkadart** |<ul><li>[ ] </li></ul>| [packages/polkadart](https://github.com/justkawal/polkadart/tree/13045810cef40cd45e0078ce9bf114d3acd756f4/packages/polkadart) | v1.0.0, see also https://pub.dev/packages/polkadart |


## General Notes

### Testing output

```zsh
Attaching to polkadart-ci
polkadart-ci  | melos run fetch_dependencies
polkadart-ci  |   └> dart run melos exec --scope="${SCOPE:-*}" -c 1 -- "dart pub get"
polkadart-ci  |      └> RUNNING
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart pub get
polkadart-ci  |      └> RUNNING (in 12 packages)
polkadart-ci  | 
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_abi:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | ink_abi: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_cli:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | ink_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | polkadart: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_cli:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | polkadart_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_keyring:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | polkadart_keyring: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_scale_codec:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | polkadart_scale_codec: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | secp256k1_ecdsa:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | secp256k1_ecdsa: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | smoldot:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | smoldot: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | sr25519:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | sr25519: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ss58:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | ss58: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_bip39:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | substrate_bip39: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_metadata:
polkadart-ci  | Resolving dependencies in `/app`...
polkadart-ci  | Downloading packages...
polkadart-ci  |   _fe_analyzer_shared 92.0.0 (93.0.0 available)
polkadart-ci  |   analyzer 9.0.0 (10.0.0 available)
polkadart-ci  |   build 4.0.3 (4.0.4 available)
polkadart-ci  |   build_runner 2.10.4 (2.10.5 available)
polkadart-ci  |   built_value 8.12.1 (8.12.2 available)
polkadart-ci  |   json_serializable 6.11.3 (6.11.4 available)
polkadart-ci  |   mustache_template 2.0.2 (2.0.3 available)
polkadart-ci  |   source_gen 4.1.1 (4.1.2 available)
polkadart-ci  |   watcher 1.1.4 (1.2.1 available)
polkadart-ci  | Got dependencies in `/app`!
polkadart-ci  | 9 packages have newer versions incompatible with dependency constraints.
polkadart-ci  | Try `dart pub outdated` for more information.
polkadart-ci  | substrate_metadata: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart pub get
polkadart-ci  |      └> SUCCESS
polkadart-ci  | melos run format
polkadart-ci  |   └> dart run melos exec --scope="${SCOPE:-*}" -c 1 -- 'dart format . --set-exit-if-changed'
polkadart-ci  |      └> RUNNING
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart format . --set-exit-if-changed
polkadart-ci  |      └> RUNNING (in 12 packages)
polkadart-ci  | 
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_abi:
polkadart-ci  | Formatted 25 files (0 changed) in 0.14 seconds.
polkadart-ci  | ink_abi: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_cli:
polkadart-ci  | Formatted 34 files (0 changed) in 0.15 seconds.
polkadart-ci  | ink_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart:
polkadart-ci  | Formatted 61 files (0 changed) in 0.15 seconds.
polkadart-ci  | polkadart: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_cli:
polkadart-ci  | Formatted 29 files (0 changed) in 0.24 seconds.
polkadart-ci  | polkadart_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_keyring:
polkadart-ci  | Formatted 19 files (0 changed) in 0.06 seconds.
polkadart-ci  | polkadart_keyring: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_scale_codec:
polkadart-ci  | Formatted 81 files (0 changed) in 0.13 seconds.
polkadart-ci  | polkadart_scale_codec: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | secp256k1_ecdsa:
polkadart-ci  | Formatted 24 files (0 changed) in 0.06 seconds.
polkadart-ci  | secp256k1_ecdsa: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | smoldot:
polkadart-ci  | Formatted 14 files (0 changed) in 0.27 seconds.
polkadart-ci  | smoldot: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | sr25519:
polkadart-ci  | Formatted 23 files (0 changed) in 0.06 seconds.
polkadart-ci  | sr25519: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ss58:
polkadart-ci  | Formatted 15 files (0 changed) in 0.06 seconds.
polkadart-ci  | ss58: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_bip39:
polkadart-ci  | Formatted 8 files (0 changed) in 0.03 seconds.
polkadart-ci  | substrate_bip39: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_metadata:
polkadart-ci  | Formatted 94 files (0 changed) in 0.32 seconds.
polkadart-ci  | substrate_metadata: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart format . --set-exit-if-changed
polkadart-ci  |      └> SUCCESS
polkadart-ci  | melos run analyze
polkadart-ci  |   └> dart run melos exec --scope="${SCOPE:-*}" -c 1 -- 'dart analyze --fatal-infos .'
polkadart-ci  |      └> RUNNING
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart analyze --fatal-infos .
polkadart-ci  |      └> RUNNING (in 12 packages)
polkadart-ci  | 
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_abi:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | ink_abi: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_cli:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | ink_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | polkadart: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_cli:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | polkadart_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_keyring:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | polkadart_keyring: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_scale_codec:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | polkadart_scale_codec: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | secp256k1_ecdsa:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | secp256k1_ecdsa: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | smoldot:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | smoldot: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | sr25519:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | sr25519: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ss58:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | ss58: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_bip39:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | substrate_bip39: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_metadata:
polkadart-ci  | Analyzing ....
polkadart-ci  | No issues found!
polkadart-ci  | substrate_metadata: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart analyze --fatal-infos .
polkadart-ci  |      └> SUCCESS
polkadart-ci  | melos run test
polkadart-ci  |   └> dart run melos exec --scope="${SCOPE:-*}" -c 1 -- 'dart test --no-chain-stack-traces --ignore-timeouts --coverage="coverage" --concurrency=1 --exclude-tags=chain'
polkadart-ci  |      └> RUNNING
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart test --no-chain-stack-traces --ignore-timeouts --coverage="coverage" --concurrency=1 --exclude-tags=chain
polkadart-ci  |      └> RUNNING (in 12 packages)
polkadart-ci  | 
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_abi:
polkadart-ci  | 00:00 +0: loading test/erc_20_v3_test.dart
polkadart-ci  | 00:00 +0: test/erc_20_v3_test.dart: decode constructor
polkadart-ci  | 00:00 +1: test/erc_20_v3_test.dart: decode event
polkadart-ci  | 00:00 +2: test/erc_20_v3_test.dart: decode message
polkadart-ci  | 00:00 +3: loading test/erc_20_v5_test.dart
polkadart-ci  | 00:00 +3: test/erc_20_v5_test.dart: decode constructor
polkadart-ci  | 00:00 +4: test/erc_20_v5_test.dart: decode event
polkadart-ci  | 00:00 +5: test/erc_20_v5_test.dart: decode anonymous event
polkadart-ci  | 00:00 +6: test/erc_20_v5_test.dart: decode message
polkadart-ci  | 00:01 +7: All tests passed!
polkadart-ci  | ink_abi: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ink_cli:
polkadart-ci  | 00:00 +0: loading test/dummy_test.dart
polkadart-ci  | 00:00 +0: test/dummy_test.dart: Dummy test
polkadart-ci  | 00:00 +1: All tests passed!
polkadart-ci  | ink_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart:
polkadart-ci  | 00:00 +0: loading test/extrinsic/extrinsic_test.dart
polkadart-ci  | 00:00 +0: test/extrinsic/extrinsic_test.dart: Bidirectional Transfer Tests - Friday1 <-> Friday2 (setUpAll)
polkadart-ci  | 00:03 +0: test/extrinsic/extrinsic_test.dart: Bidirectional Transfer Tests - Friday1 <-> Friday2 Transfer 0.1 WND from Friday1 to Friday2
polkadart-ci  | 00:12 +1: test/extrinsic/extrinsic_test.dart: Bidirectional Transfer Tests - Friday1 <-> Friday2 Transfer 0.1 WND back from Friday2 to Friday1
polkadart-ci  | 00:20 +2: test/extrinsic/extrinsic_test.dart: Bidirectional Transfer Tests - Friday1 <-> Friday2 Alternative: Transfer using fromChainData mode - Friday1 → Friday2
polkadart-ci  | 00:20 +3: test/extrinsic/extrinsic_test.dart: Bidirectional Transfer Tests - Friday1 <-> Friday2 Alternative: Transfer using fromChainData mode - Friday2 → Friday1
polkadart-ci  | 00:20 +4: test/extrinsic/extrinsic_test.dart: Bidirectional Transfer Tests - Friday1 <-> Friday2 (tearDownAll)
polkadart-ci  | 00:21 +4: loading test/apis/system_test.dart
polkadart-ci  | 00:21 +4: test/apis/system_test.dart: SystemApi name
polkadart-ci  | 00:21 +5: test/apis/system_test.dart: SystemApi version
polkadart-ci  | 00:21 +6: test/apis/system_test.dart: SystemApi chain
polkadart-ci  | 00:21 +7: test/apis/system_test.dart: SystemApi chainType
polkadart-ci  | 00:21 +8: test/apis/system_test.dart: SystemApi health
polkadart-ci  | 00:21 +9: test/apis/system_test.dart: SystemApi localPeerId
polkadart-ci  | 00:21 +10: test/apis/system_test.dart: SystemApi localListenAddresses
polkadart-ci  | 00:21 +11: test/apis/system_test.dart: SystemApi peers
polkadart-ci  | 00:21 +12: test/apis/system_test.dart: SystemApi accountNextIndex
polkadart-ci  | 00:21 +13: test/apis/system_test.dart: SystemApi syncState
polkadart-ci  | 00:22 +14: All tests passed!
polkadart-ci  | polkadart: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_cli:
polkadart-ci  | 00:00 +0: loading test/typegen/composite_test.dart
polkadart-ci  | 00:00 +0: test/typegen/composite_test.dart: CompositeGenerator Point(x, y)
polkadart-ci  | 00:01 +1: loading test/typegen/typedef_test.dart
polkadart-ci  | 00:01 +1: test/typegen/typedef_test.dart: TypeDefGenerator Primitive u8
polkadart-ci  | 00:01 +2: test/typegen/typedef_test.dart: TypeDefGenerator sequence typedef
polkadart-ci  | 00:01 +3: test/typegen/typedef_test.dart: TypeDefGenerator composite typedef
polkadart-ci  | 00:02 +4: All tests passed!
polkadart-ci  | polkadart_cli: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_keyring:
polkadart-ci  | 00:00 +0: loading test/pairs_test.dart
polkadart-ci  | 00:00 +0: test/pairs_test.dart: Pairs Class Adding and Retrieving KeyPairs
polkadart-ci  | 00:00 +1: test/pairs_test.dart: Pairs Class Retrieving KeyPairs by PublicKey
polkadart-ci  | 00:00 +2: test/pairs_test.dart: Pairs Class Removing KeyPairs
polkadart-ci  | 00:00 +3: test/pairs_test.dart: Pairs Class Removing All KeyPairs
polkadart-ci  | 00:00 +4: test/pairs_test.dart: Pairs Class Getting Public Keys and Addresses
polkadart-ci  | 00:00 +5: test/pairs_test.dart: Pairs Class Getting All KeyPairs
polkadart-ci  | 00:00 +6: loading test/keypair_test.dart
polkadart-ci  | 00:00 +6: test/keypair_test.dart: Ed25519 fromSeed
polkadart-ci  | 00:01 +7: test/keypair_test.dart: Ed25519 fromMnemonic
polkadart-ci  | 00:01 +8: test/keypair_test.dart: Ed25519 sign and verify
polkadart-ci  | 00:01 +9: test/keypair_test.dart: Ed25519 lock
polkadart-ci  | 00:01 +10: test/keypair_test.dart: Ed25519 unlockFromMnemonic
polkadart-ci  | 00:01 +11: test/keypair_test.dart: Ed25519 unlockFromSeed
polkadart-ci  | 00:02 +12: loading test/suri_sr25519_test.dart
polkadart-ci  | 00:02 +12: test/suri_sr25519_test.dart: Sr25519 Suri Test
polkadart-ci  | 00:06 +13: loading test/keyring_test.dart
polkadart-ci  | 00:06 +13: test/keyring_test.dart: Keyring Class: Creating KeyPairs from Mnemonic
polkadart-ci  | 00:06 +14: test/keyring_test.dart: Keyring Class: Adding and Retrieving KeyPairs
polkadart-ci  | 00:06 +15: test/keyring_test.dart: Keyring Class: Retrieving KeyPairs by PublicKey
polkadart-ci  | 00:06 +16: test/keyring_test.dart: Keyring Class: Removing KeyPairs
polkadart-ci  | 00:07 +17: test/keyring_test.dart: Keyring Class: Encoding and Decoding Addresses
polkadart-ci  | 00:07 +18: test/keyring_test.dart: Keyring Class: Getting All Public Keys
polkadart-ci  | 00:07 +19: test/keyring_test.dart: Keyring Class: Getting All Addresses
polkadart-ci  | 00:07 +20: test/keyring_test.dart: Keyring Class: Getting All KeyPairs
polkadart-ci  | 00:07 +21: test/keyring_test.dart: Keyring Class: Removing All KeyPairs
polkadart-ci  | 00:07 +22: test/keyring_test.dart: Keyring Class: Signing and Verifying
polkadart-ci  | 00:07 +23: loading test/keypair_ecdsa_test.dart
polkadart-ci  | 00:07 +23: test/keypair_ecdsa_test.dart: Ecdsa test cases test //Alice
polkadart-ci  | 00:08 +24: test/keypair_ecdsa_test.dart: Ecdsa test cases adds the pair
polkadart-ci  | 00:08 +25: test/keypair_ecdsa_test.dart: Ecdsa test cases test adds from a mnemonic
polkadart-ci  | 00:08 +26: test/keypair_ecdsa_test.dart: Ecdsa test cases allows publicKeys retrieval
polkadart-ci  | 00:08 +27: test/keypair_ecdsa_test.dart: Ecdsa test cases signs and verifies
polkadart-ci  | 00:08 +28: test/keypair_ecdsa_test.dart: Ecdsa test cases secp256k1PairFromSeed generates a valid publicKey/secretKey pair (u8a)
polkadart-ci  | 00:08 +29: test/keypair_ecdsa_test.dart: Ecdsa test cases secp256k1PairFromSeed generates a valid publicKey/secretKey pair (u8a)
polkadart-ci  | 00:08 +30: loading test/keypair_sr25519_test.dart
polkadart-ci  | 00:08 +30: test/keypair_sr25519_test.dart: Sr25519 test cases test //Alice
polkadart-ci  | 00:11 +31: test/keypair_sr25519_test.dart: Sr25519 test cases test //9007199254740991
polkadart-ci  | 00:11 +32: test/keypair_sr25519_test.dart: Sr25519 test cases test //900719925474099999
polkadart-ci  | 00:11 +33: test/keypair_sr25519_test.dart: Sr25519 test cases test //Alice via dev seed (2-byte encoding)
polkadart-ci  | 00:11 +34: test/keypair_sr25519_test.dart: Sr25519 test cases test adds the pair: seedTwo
polkadart-ci  | 00:11 +35: test/keypair_sr25519_test.dart: Sr25519 test cases test adds from a mnemonic
polkadart-ci  | 00:12 +36: test/keypair_sr25519_test.dart: Sr25519 test cases allows publicKeys retrieval
polkadart-ci  | 00:12 +37: test/keypair_sr25519_test.dart: Sr25519 test cases signs and verifies
polkadart-ci  | 00:13 +38: All tests passed!
polkadart-ci  | polkadart_keyring: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | polkadart_scale_codec:
polkadart-ci  | 00:00 +0: loading test/direct_tests/i8_test.dart
polkadart-ci  | 00:00 +0: test/direct_tests/i8_test.dart: I8 Decode Test: Lowest value decoding
polkadart-ci  | 00:00 +1: test/direct_tests/i8_test.dart: I8 Decode Test: Highest value decoding
polkadart-ci  | 00:00 +2: test/direct_tests/i8_test.dart: I8 Encode Test: Lowest value encoding
polkadart-ci  | 00:00 +3: test/direct_tests/i8_test.dart: I8 Encode Test: Highest value encoding
polkadart-ci  | 00:00 +4: loading test/direct_tests/i32_test.dart
polkadart-ci  | 00:00 +4: test/direct_tests/i32_test.dart: I32 Decode Test: Lowest value decoding
polkadart-ci  | 00:00 +5: test/direct_tests/i32_test.dart: I32 Decode Test: Highest value decoding
polkadart-ci  | 00:00 +6: test/direct_tests/i32_test.dart: I32 Encode Test: Lowest value encoding
polkadart-ci  | 00:00 +7: test/direct_tests/i32_test.dart: I32 Encode Test: Highest value encoding
polkadart-ci  | 00:00 +8: loading test/direct_tests/u128_test.dart
polkadart-ci  | 00:00 +8: test/direct_tests/u128_test.dart: U128 Decode Test: Lowest value decoding
polkadart-ci  | 00:00 +9: test/direct_tests/u128_test.dart: U128 Decode Test: Highest value decoding
polkadart-ci  | 00:00 +10: test/direct_tests/u128_test.dart: U128 Encode Test: Lowest value encoding
polkadart-ci  | 00:00 +11: test/direct_tests/u128_test.dart: U128 Encode Test: Highest value encoding
polkadart-ci  | 00:00 +12: loading test/direct_tests/option_test.dart
polkadart-ci  | 00:01 +12: test/direct_tests/option_test.dart: Option Encode Test: Given a Option.some([3, true]) it should be encoded to 0x010c01
polkadart-ci  | 00:01 +13: test/direct_tests/option_test.dart: Option Encode Test: Given a None it should be encoded to 0x00
polkadart-ci  | 00:01 +14: test/direct_tests/option_test.dart: Option Encode Test: Given a Option.some(true) it should be encoded to 0x0101
polkadart-ci  | 00:01 +15: test/direct_tests/option_test.dart: Option Encode Test: Given a Option.some(false) it should be encoded to 0x0100
polkadart-ci  | 00:01 +16: test/direct_tests/option_test.dart: Option Encode Test: Given a Option.some(None) it should be encoded to 0x0100
polkadart-ci  | 00:01 +17: test/direct_tests/option_test.dart: Option Encode Test: Given a Option.some(Option.some(true)) it should be encoded to 0x010101
polkadart-ci  | 00:01 +18: test/direct_tests/option_test.dart: Option Encode Test: Given a Option.some(Option.some(false)) it should be encoded to 0x010100
polkadart-ci  | 00:01 +19: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x010c01 it should be decoded to Option.some([3, true])
polkadart-ci  | 00:01 +20: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x00 it should be decoded to None
polkadart-ci  | 00:01 +21: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x0101 it should be decoded to Option.some(true)
polkadart-ci  | 00:01 +22: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x0100 it should be decoded to Option.some(false)
polkadart-ci  | 00:01 +23: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x0100 it should be decoded to Option.some(None)
polkadart-ci  | 00:01 +24: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x010101 it should be decoded to Option.some(Option.some(true))
polkadart-ci  | 00:01 +25: test/direct_tests/option_test.dart: Option Decode Test: Given a 0x010100 it should be decoded to Option.some(Option.some(false))
polkadart-ci  | 00:01 +26: loading test/direct_tests/compact_test.dart
polkadart-ci  | 00:01 +26: test/direct_tests/compact_test.dart: Compact sizeHint: Length of input and output should match
polkadart-ci  | 00:01 +27: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 0
polkadart-ci  | 00:01 +28: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 63
polkadart-ci  | 00:01 +29: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 64
polkadart-ci  | 00:01 +30: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 16383
polkadart-ci  | 00:01 +31: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 16384
polkadart-ci  | 00:01 +32: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 1073741823
polkadart-ci  | 00:01 +33: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 1073741824
polkadart-ci  | 00:01 +34: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 4294967295
polkadart-ci  | 00:01 +35: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 4294967296
polkadart-ci  | 00:01 +36: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 1099511627776
polkadart-ci  | 00:01 +37: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 281474976710656
polkadart-ci  | 00:01 +38: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 72057594037927935
polkadart-ci  | 00:01 +39: test/direct_tests/compact_test.dart: Compact sizeHint: Test for size hint at 72057594037927936
polkadart-ci  | 00:01 +40: test/direct_tests/compact_test.dart: Compact decoding: Length of input and output should match
polkadart-ci  | 00:01 +41: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [0] at index 0
polkadart-ci  | 00:01 +42: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [252] at index 1
polkadart-ci  | 00:01 +43: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [1, 1] at index 2
polkadart-ci  | 00:01 +44: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [253, 255] at index 3
polkadart-ci  | 00:01 +45: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [2, 0, 1, 0] at index 4
polkadart-ci  | 00:01 +46: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [254, 255, 255, 255] at index 5
polkadart-ci  | 00:01 +47: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [3, 0, 0, 0, 64] at index 6
polkadart-ci  | 00:01 +48: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [3, 255, 255, 255, 255] at index 7
polkadart-ci  | 00:01 +49: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [7, 0, 0, 0, 0, 1] at index 8
polkadart-ci  | 00:01 +50: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [11, 0, 0, 0, 0, 0, 1] at index 9
polkadart-ci  | 00:01 +51: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [15, 0, 0, 0, 0, 0, 0, 1] at index 10
polkadart-ci  | 00:01 +52: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [15, 255, 255, 255, 255, 255, 255, 255] at index 11
polkadart-ci  | 00:01 +53: test/direct_tests/compact_test.dart: Compact decoding: Testing decoding of [19, 0, 0, 0, 0, 0, 0, 0, 1] at index 12
polkadart-ci  | 00:01 +54: test/direct_tests/compact_test.dart: Compact encoding: Length of input and output should match
polkadart-ci  | 00:01 +55: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 0 at index 0
polkadart-ci  | 00:01 +56: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 63 at index 1
polkadart-ci  | 00:01 +57: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 64 at index 2
polkadart-ci  | 00:01 +58: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 16383 at index 3
polkadart-ci  | 00:01 +59: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 16384 at index 4
polkadart-ci  | 00:01 +60: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 1073741823 at index 5
polkadart-ci  | 00:01 +61: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 1073741824 at index 6
polkadart-ci  | 00:01 +62: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 4294967295 at index 7
polkadart-ci  | 00:01 +63: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 4294967296 at index 8
polkadart-ci  | 00:01 +64: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 1099511627776 at index 9
polkadart-ci  | 00:01 +65: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 281474976710656 at index 10
polkadart-ci  | 00:01 +66: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 72057594037927935 at index 11
polkadart-ci  | 00:01 +67: test/direct_tests/compact_test.dart: Compact encoding: Testing encoding of 72057594037927936 at index 12
polkadart-ci  | 00:01 +68: loading test/direct_tests/i256_test.dart
polkadart-ci  | 00:01 +68: test/direct_tests/i256_test.dart: I256 Decode Test: Lowest value decoding
polkadart-ci  | 00:01 +69: test/direct_tests/i256_test.dart: I256 Decode Test: Highest value decoding
polkadart-ci  | 00:01 +70: test/direct_tests/i256_test.dart: I256 Encode Test: Lowest value encoding
polkadart-ci  | 00:01 +71: test/direct_tests/i256_test.dart: I256 Encode Test: Highest value encoding
polkadart-ci  | 00:02 +72: loading test/direct_tests/bit_sequence_test.dart
polkadart-ci  | 00:02 +72: test/direct_tests/bit_sequence_test.dart: BitSequence(U8, LSB) codec works
polkadart-ci  | 00:02 +73: test/direct_tests/bit_sequence_test.dart: BitSequence(U16, LSB) codec works
polkadart-ci  | 00:02 +74: test/direct_tests/bit_sequence_test.dart: BitSequence(U32, LSB) codec works
polkadart-ci  | 00:02 +75: test/direct_tests/bit_sequence_test.dart: BitSequence(U64, LSB) codec works
polkadart-ci  | 00:02 +76: test/direct_tests/bit_sequence_test.dart: BitSequence(U8, MSB) codec works
polkadart-ci  | 00:02 +77: test/direct_tests/bit_sequence_test.dart: BitSequence(U16, MSB) codec works
polkadart-ci  | 00:02 +78: test/direct_tests/bit_sequence_test.dart: BitSequence(U32, MSB) codec works
polkadart-ci  | 00:02 +79: test/direct_tests/bit_sequence_test.dart: BitSequence(U64, MSB) codec works
polkadart-ci  | 00:02 +80: loading test/direct_tests/i64_test.dart
polkadart-ci  | 00:02 +80: test/direct_tests/i64_test.dart: I64 Decode Test: Lowest value decoding
polkadart-ci  | 00:02 +81: test/direct_tests/i64_test.dart: I64 Decode Test: Highest value decoding
polkadart-ci  | 00:02 +82: test/direct_tests/i64_test.dart: I64 Encode Test: Lowest value encoding
polkadart-ci  | 00:02 +83: test/direct_tests/i64_test.dart: I64 Encode Test: Highest value encoding
polkadart-ci  | 00:02 +84: loading test/direct_tests/array_test.dart
polkadart-ci  | 00:02 +84: test/direct_tests/array_test.dart: Array Codec Encode Test When value [1, 2, 3, 4] is encoded then it returns 0x01020304
polkadart-ci  | 00:02 +85: test/direct_tests/array_test.dart: Array Codec Encode Test When value [[1, 2], [3, 4]] is encoded then it returns 0x01020304
polkadart-ci  | 00:02 +86: test/direct_tests/array_test.dart: Array Codec Encode Test When value [5, 6, 7, 8] is encoded then it returns 0x05060708
polkadart-ci  | 00:02 +87: test/direct_tests/array_test.dart: Array Codec Encode Test When value [5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20] is encoded then it returns 0x05060708090a0b0c0d0e0f1011121314
polkadart-ci  | 00:02 +88: test/direct_tests/array_test.dart: Array Codec Encode Test When value [[0, true], [1, false], [2, true], [3, false]] is encoded then it returns 0x0001010002010300
polkadart-ci  | 00:02 +89: test/direct_tests/array_test.dart: Array Codec Decode Test When value 0x01020304 is decoded then it returns [1, 2, 3, 4]
polkadart-ci  | 00:02 +90: test/direct_tests/array_test.dart: Array Codec Decode Test When value 0x01020304 is decoded then it returns [[1, 2], [3, 4]]
polkadart-ci  | 00:02 +91: test/direct_tests/array_test.dart: Array Codec Decode Test When value 0x05060708 is decoded then it returns [5, 6, 7, 8]
polkadart-ci  | 00:02 +92: test/direct_tests/array_test.dart: Array Codec Decode Test When value 0x05060708090a0b0c0d0e0f1011121314 is decoded then it returns [5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
polkadart-ci  | 00:02 +93: test/direct_tests/array_test.dart: Array Codec Decode Test When value 0x0001010002010300 is decoded then it returns [[0, true], [1, false], [2, true], [3, false]]
polkadart-ci  | 00:03 +94: loading test/direct_tests/composite_test.dart
polkadart-ci  | 00:03 +94: test/direct_tests/composite_test.dart: Composite Encode Test When value {"a": 42, "b": true} is encoded then it returns 0x2a01
polkadart-ci  | 00:03 +95: test/direct_tests/composite_test.dart: Composite Encode Test When Composite is encoded then it returns correct hex 0x0838546869732069732061206e6f7465104b69776901014448657920466f6f642077617320676f6f64
polkadart-ci  | 00:03 +96: test/direct_tests/composite_test.dart: Composite Decode Test When value 0x2a01 is decoded then it returns {"a": 42, "b": true}
polkadart-ci  | 00:03 +97: test/direct_tests/composite_test.dart: Composite Decode Test When Composite is decoded then it returns correct value {"index": 8, "note": "This is a note", "Juice": {"name": "Kiwi", "ounces": 1}, "Remarks": "Hey Food was good"}
polkadart-ci  | 00:03 +98: loading test/direct_tests/simple_enum_test.dart
polkadart-ci  | 00:03 +98: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.fromList Encode should encode and decode
polkadart-ci  | 00:03 +99: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.fromList Encode should throw error when invalid value
polkadart-ci  | 00:03 +100: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.sparse Encode should encode and decode
polkadart-ci  | 00:03 +101: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.sparse Encode should throw error when invalid value
polkadart-ci  | 00:03 +102: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.fromList Decode should encode and decode
polkadart-ci  | 00:03 +103: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.fromList Decode should throw error when invalid index
polkadart-ci  | 00:03 +104: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.sparse Decode should encode and decode
polkadart-ci  | 00:03 +105: test/direct_tests/simple_enum_test.dart: SimpleEnumCodec.sparse Decode should throw error when invalid index
polkadart-ci  | 00:03 +106: loading test/direct_tests/u8_test.dart
polkadart-ci  | 00:03 +106: test/direct_tests/u8_test.dart: U8 Decode Test: Lowest value decoding
polkadart-ci  | 00:03 +107: test/direct_tests/u8_test.dart: U8 Decode Test: Highest value decoding
polkadart-ci  | 00:03 +108: test/direct_tests/u8_test.dart: U8 Encode Test: Lowest value encoding
polkadart-ci  | 00:03 +109: test/direct_tests/u8_test.dart: U8 Encode Test: Highest value encoding
polkadart-ci  | 00:04 +110: loading test/direct_tests/result_codec_test.dart
polkadart-ci  | 00:04 +110: test/direct_tests/result_codec_test.dart: Result Codec Encode Test Result.ok
polkadart-ci  | 00:04 +111: test/direct_tests/result_codec_test.dart: Result Codec Encode Test Result.error
polkadart-ci  | 00:04 +112: test/direct_tests/result_codec_test.dart: Result Codec Decode Test Result.ok
polkadart-ci  | 00:04 +113: test/direct_tests/result_codec_test.dart: Result Codec Decode Test Result.error
polkadart-ci  | 00:04 +114: loading test/direct_tests/complex_enum_test.dart
polkadart-ci  | 00:04 +114: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.sparse Encode Test should encode and decode
polkadart-ci  | 00:04 +115: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.sparse Encode Test should throw error when invalid value
polkadart-ci  | 00:04 +116: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.fromList Encode Test should encode and decode
polkadart-ci  | 00:04 +117: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.fromList Encode Test should throw error when invalid value
polkadart-ci  | 00:04 +118: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.sparse Decode Test should decode and encode
polkadart-ci  | 00:04 +119: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.sparse Decode Test should throw error when invalid index
polkadart-ci  | 00:04 +120: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.fromList Decode Test should decode and encode
polkadart-ci  | 00:04 +121: test/direct_tests/complex_enum_test.dart: ComplexEnumCodec.fromList Decode Test should throw error when invalid index
polkadart-ci  | 00:04 +122: loading test/direct_tests/u64_test.dart
polkadart-ci  | 00:04 +122: test/direct_tests/u64_test.dart: U64 Decode Test: Lowest value decoding
polkadart-ci  | 00:04 +123: test/direct_tests/u64_test.dart: U64 Decode Test: Highest value decoding
polkadart-ci  | 00:04 +124: test/direct_tests/u64_test.dart: U64 Encode Test: Lowest value encoding
polkadart-ci  | 00:04 +125: test/direct_tests/u64_test.dart: U64 Encode Test: Highest value encoding
polkadart-ci  | 00:05 +126: loading test/direct_tests/u256_test.dart
polkadart-ci  | 00:05 +126: test/direct_tests/u256_test.dart: U256 Decode Test: Lowest value decoding
polkadart-ci  | 00:05 +127: test/direct_tests/u256_test.dart: U256 Decode Test: Highest value decoding
polkadart-ci  | 00:05 +128: test/direct_tests/u256_test.dart: U256 Encode Test: Lowest value encoding
polkadart-ci  | 00:05 +129: test/direct_tests/u256_test.dart: U256 Encode Test: Highest value encoding
polkadart-ci  | 00:05 +130: loading test/direct_tests/u32_test.dart
polkadart-ci  | 00:05 +130: test/direct_tests/u32_test.dart: U32 Decode Test: Lowest value decoding
polkadart-ci  | 00:05 +131: test/direct_tests/u32_test.dart: U32 Decode Test: Highest value decoding
polkadart-ci  | 00:05 +132: test/direct_tests/u32_test.dart: U32 Encode Test: Lowest value encoding
polkadart-ci  | 00:05 +133: test/direct_tests/u32_test.dart: U32 Encode Test: Highest value encoding
polkadart-ci  | 00:05 +134: loading test/direct_tests/str_test.dart
polkadart-ci  | 00:05 +134: test/direct_tests/str_test.dart: StrCodec Tests Should encode and decode normal strings correctly
polkadart-ci  | 00:05 +135: test/direct_tests/str_test.dart: StrCodec Tests Should encode and decode empty strings correctly
polkadart-ci  | 00:05 +136: test/direct_tests/str_test.dart: StrCodec Tests Should encode and decode unicode strings correctly
polkadart-ci  | 00:05 +137: test/direct_tests/str_test.dart: StrCodec Tests Should strip trailing null bytes when decoding
polkadart-ci  | 00:05 +138: test/direct_tests/str_test.dart: StrCodec Tests Should preserve null bytes in the middle of strings
polkadart-ci  | 00:05 +139: test/direct_tests/str_test.dart: StrCodec Tests Should handle strings that are exactly the encoded length
polkadart-ci  | 00:05 +140: test/direct_tests/str_test.dart: StrCodec Tests Should calculate correct size hint
polkadart-ci  | 00:05 +141: loading test/direct_tests/u16_test.dart
polkadart-ci  | 00:06 +141: test/direct_tests/u16_test.dart: U16 Decode Test: Lowest value decoding
polkadart-ci  | 00:06 +142: test/direct_tests/u16_test.dart: U16 Decode Test: Highest value decoding
polkadart-ci  | 00:06 +143: test/direct_tests/u16_test.dart: U16 Encode Test: Lowest value encoding
polkadart-ci  | 00:06 +144: test/direct_tests/u16_test.dart: U16 Encode Test: Highest value encoding
polkadart-ci  | 00:06 +145: loading test/direct_tests/compact_bigint_test.dart
polkadart-ci  | 00:06 +145: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Length of input and output should match
polkadart-ci  | 00:06 +146: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 0
polkadart-ci  | 00:06 +147: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 63
polkadart-ci  | 00:06 +148: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 64
polkadart-ci  | 00:06 +149: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 16383
polkadart-ci  | 00:06 +150: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 16384
polkadart-ci  | 00:06 +151: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 1073741823
polkadart-ci  | 00:06 +152: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 1073741824
polkadart-ci  | 00:06 +153: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 4294967295
polkadart-ci  | 00:06 +154: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 4294967296
polkadart-ci  | 00:06 +155: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 1099511627776
polkadart-ci  | 00:06 +156: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 281474976710656
polkadart-ci  | 00:06 +157: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 72057594037927935
polkadart-ci  | 00:06 +158: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 72057594037927936
polkadart-ci  | 00:06 +159: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 18446744073709551615
polkadart-ci  | 00:06 +160: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 18446744073709551616
polkadart-ci  | 00:06 +161: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 4722366482869645213696
polkadart-ci  | 00:06 +162: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 1208925819614629174706176
polkadart-ci  | 00:06 +163: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 309485009821345068724781056
polkadart-ci  | 00:06 +164: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 79228162514264337593543950336
polkadart-ci  | 00:06 +165: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 20282409603651670423947251286016
polkadart-ci  | 00:06 +166: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 5192296858534827628530496329220096
polkadart-ci  | 00:06 +167: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 1329227995784915872903807060280344575
polkadart-ci  | 00:06 +168: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 1329227995784915872903807060280344576
polkadart-ci  | 00:06 +169: test/direct_tests/compact_bigint_test.dart: CompactBigInt sizeHint: Test for size hint at 340282366920938463463374607431768211455
polkadart-ci  | 00:06 +170: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Length of input and output should match
polkadart-ci  | 00:06 +171: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [0] at index 0
polkadart-ci  | 00:06 +172: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [252] at index 1
polkadart-ci  | 00:06 +173: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [1, 1] at index 2
polkadart-ci  | 00:06 +174: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [253, 255] at index 3
polkadart-ci  | 00:06 +175: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [2, 0, 1, 0] at index 4
polkadart-ci  | 00:06 +176: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [254, 255, 255, 255] at index 5
polkadart-ci  | 00:06 +177: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [3, 0, 0, 0, 64] at index 6
polkadart-ci  | 00:06 +178: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [3, 255, 255, 255, 255] at index 7
polkadart-ci  | 00:06 +179: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [7, 0, 0, 0, 0, 1] at index 8
polkadart-ci  | 00:06 +180: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [11, 0, 0, 0, 0, 0, 1] at index 9
polkadart-ci  | 00:06 +181: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [15, 0, 0, 0, 0, 0, 0, 1] at index 10
polkadart-ci  | 00:06 +182: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [15, 255, 255, 255, 255, 255, 255, 255] at index 11
polkadart-ci  | 00:06 +183: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [19, 0, 0, 0, 0, 0, 0, 0, 1] at index 12
polkadart-ci  | 00:06 +184: test/direct_tests/compact_bigint_test.dart: CompactBigInt decoding: Testing decoding of [19, 255, 255, 255, 255, 255, 255, 255, 255] at index 13
polkadart-ci  | 00:06 +185: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Length of input and output should match
polkadart-ci  | 00:06 +186: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 0 at index 0
polkadart-ci  | 00:06 +187: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 63 at index 1
polkadart-ci  | 00:06 +188: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 64 at index 2
polkadart-ci  | 00:06 +189: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 16383 at index 3
polkadart-ci  | 00:06 +190: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 16384 at index 4
polkadart-ci  | 00:06 +191: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 1073741823 at index 5
polkadart-ci  | 00:06 +192: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 1073741824 at index 6
polkadart-ci  | 00:06 +193: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 4294967295 at index 7
polkadart-ci  | 00:06 +194: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 4294967296 at index 8
polkadart-ci  | 00:06 +195: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 1099511627776 at index 9
polkadart-ci  | 00:06 +196: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 281474976710656 at index 10
polkadart-ci  | 00:06 +197: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 72057594037927935 at index 11
polkadart-ci  | 00:06 +198: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 72057594037927936 at index 12
polkadart-ci  | 00:06 +199: test/direct_tests/compact_bigint_test.dart: CompactBigInt encoding: Testing encoding of 18446744073709551615 at index 13
polkadart-ci  | 00:06 +200: loading test/direct_tests/tuple_test.dart
polkadart-ci  | 00:06 +200: test/direct_tests/tuple_test.dart: encode tuple to hex  Given a list with compact unsigned integer and boolean it should be encoded to correct value
polkadart-ci  | 00:06 +201: test/direct_tests/tuple_test.dart: encode tuple to hex  Given a list of one String and one unsigned 8bit integer it should be encoded to correct value
polkadart-ci  | 00:06 +202: test/direct_tests/tuple_test.dart: encode tuple to hex  Given a list of one Vec<String> it should be encoded to correct value
polkadart-ci  | 00:06 +203: test/direct_tests/tuple_test.dart: encode tuple to hex  Given a ((Str, Str), (U8, U8)) it should be encoded to correct value
polkadart-ci  | 00:06 +204: test/direct_tests/tuple_test.dart: decode tuple from hex  Given a hex with compact unsigned integer and boolean it should be decoded to correct value
polkadart-ci  | 00:06 +205: test/direct_tests/tuple_test.dart: decode tuple from hex  Given a hex of one String and one unsigned 8bit integer it should be decoded to correct value
polkadart-ci  | 00:06 +206: test/direct_tests/tuple_test.dart: decode tuple from hex  Given a hex of one Vec<String> it should be decoded to correct value
polkadart-ci  | 00:06 +207: test/direct_tests/tuple_test.dart: decode tuple from hex  Given a hex of ((Str, Str), (U8, U8)) it should be decoded to correct value
polkadart-ci  | 00:07 +208: loading test/direct_tests/b_tree_map_test.dart
polkadart-ci  | 00:07 +208: test/direct_tests/b_tree_map_test.dart: BTreeMap Encode Test: Given a {42: true} it should be encoded to 0x042a01
polkadart-ci  | 00:07 +209: test/direct_tests/b_tree_map_test.dart: BTreeMap Encode Test: When value {{632: false}: true} is encoded then it returns 0x0404780200000001
polkadart-ci  | 00:07 +210: test/direct_tests/b_tree_map_test.dart: BTreeMap Encode Test: When value {{"1291": true}: false} is encoded then it returns 0x040410313239310100
polkadart-ci  | 00:07 +211: test/direct_tests/b_tree_map_test.dart: BTreeMap Encode Test: When value {[42, true]: false} is encoded then it returns 0x042a0100
polkadart-ci  | 00:07 +212: test/direct_tests/b_tree_map_test.dart: BTreeMap Decode Test: Given a 0x042a01 it should be decoded to {42: true}
polkadart-ci  | 00:07 +213: test/direct_tests/b_tree_map_test.dart: BTreeMap Decode Test: When value 0x0404780200000001 is decoded then it returns {{632: false}: true}
polkadart-ci  | 00:07 +214: test/direct_tests/b_tree_map_test.dart: BTreeMap Decode Test: When value 0x040410313239310100 is decoded then it returns {{"1291": true}: false}
polkadart-ci  | 00:07 +215: test/direct_tests/b_tree_map_test.dart: BTreeMap Decode Test: When value 0x042a0100 is decoded then it returns {[42, true]: false}
polkadart-ci  | 00:07 +216: loading test/direct_tests/i16_test.dart
polkadart-ci  | 00:07 +216: test/direct_tests/i16_test.dart: I16 Decode Test: Lowest value decoding
polkadart-ci  | 00:07 +217: test/direct_tests/i16_test.dart: I16 Decode Test: Highest value decoding
polkadart-ci  | 00:07 +218: test/direct_tests/i16_test.dart: I16 Encode Test: Lowest value encoding
polkadart-ci  | 00:07 +219: test/direct_tests/i16_test.dart: I16 Encode Test: Highest value encoding
polkadart-ci  | 00:07 +220: loading test/direct_tests/i128_test.dart
polkadart-ci  | 00:07 +220: test/direct_tests/i128_test.dart: I128 Decode Test: Lowest value decoding
polkadart-ci  | 00:07 +221: test/direct_tests/i128_test.dart: I128 Decode Test: Highest value decoding
polkadart-ci  | 00:07 +222: test/direct_tests/i128_test.dart: I128 Encode Test: Lowest value encoding
polkadart-ci  | 00:07 +223: test/direct_tests/i128_test.dart: I128 Encode Test: Highest value encoding
polkadart-ci  | 00:08 +224: All tests passed!
polkadart-ci  | polkadart_scale_codec: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | secp256k1_ecdsa:
polkadart-ci  | 00:00 +0: loading test/sign_test.dart
polkadart-ci  | 00:00 +0: test/sign_test.dart: Sign Test fromCompactHex() roundtrip
polkadart-ci  | 00:00 +1: test/sign_test.dart: Sign Test .fromDERHex() roundtrip
polkadart-ci  | 00:00 +2: test/sign_test.dart: sign() create deterministic signatures with RFC 6979
polkadart-ci  | 00:02 +3: test/sign_test.dart: sign() not create invalid deterministic signatures with RFC 6979
polkadart-ci  | 00:02 +4: test/sign_test.dart: sign() create correct DER encoding against libsecp256k1
polkadart-ci  | 00:02 +5: test/sign_test.dart: sign() handle {extraData} option
polkadart-ci  | 00:02 +6: loading test/expand_keys_test.dart
polkadart-ci  | 00:02 +6: test/expand_keys_test.dart: Expand Keys expand a key
polkadart-ci  | 00:02 +7: test/expand_keys_test.dart: Expand Keys should compress the uncompressed key
polkadart-ci  | 00:02 +8: loading test/public_keys_test.dart
polkadart-ci  | 00:03 +8: test/public_keys_test.dart: (setUpAll)
polkadart-ci  | 00:03 +8: test/public_keys_test.dart: test keys
polkadart-ci  | 00:03 +9: test/public_keys_test.dart: (tearDownAll)
polkadart-ci  | 00:03 +9: loading test/verify_test.dart
polkadart-ci  | 00:03 +9: test/verify_test.dart: verify() verify signature
polkadart-ci  | 00:03 +10: test/verify_test.dart: verify()  not verify signature with wrong public key
polkadart-ci  | 00:03 +11: test/verify_test.dart: verify() not verify signature with wrong hash
polkadart-ci  | 00:03 +12: test/verify_test.dart: verify() verify random signatures
polkadart-ci  | 00:03 +13: test/verify_test.dart: verify() not verify signature with invalid r/s
polkadart-ci  | 00:03 +14: test/verify_test.dart: verify() not verify msg = curve order
polkadart-ci  | 00:03 +15: test/verify_test.dart: verify() verify non-strict msg bb5a...
polkadart-ci  | 00:03 +16: test/verify_test.dart: verify() not verify invalid deterministic signatures with RFC 6979
polkadart-ci  | 00:04 +17: loading test/compress_keys_test.dart
polkadart-ci  | 00:04 +17: test/compress_keys_test.dart: Compress Keys should return the already compressed key as is
polkadart-ci  | 00:04 +18: test/compress_keys_test.dart: Compress Keys should compress the uncompressed key
polkadart-ci  | 00:04 +19: loading test/recover_public_key_test.dart
polkadart-ci  | 00:04 +19: test/recover_public_key_test.dart: recoverPublicKey() recover public key from recovery bit
polkadart-ci  | 00:04 +20: test/recover_public_key_test.dart: recoverPublicKey() handle all-zeros msghash
polkadart-ci  | 00:04 +21: test/recover_public_key_test.dart: recoverPublicKey() handle RFC 6979 vectors
polkadart-ci  | 00:17 +22: loading test/privates_test.dart
polkadart-ci  | 00:17 +22: test/privates_test.dart: Privates Test fromHex() assertValidity
polkadart-ci  | 00:18 +23: test/privates_test.dart: Privates Test PrivateKey.fromHex()
polkadart-ci  | 00:18 +24: test/privates_test.dart: Privates Test #toHex(compressed)
polkadart-ci  | 00:18 +25: test/privates_test.dart: Privates Test #toHex() roundtrip
polkadart-ci  | 00:18 +26: test/privates_test.dart: Privates Test #add(other)
polkadart-ci  | 00:18 +27: test/privates_test.dart: Privates Test #multiply(privateKey)
polkadart-ci  | 00:18 +28: All tests passed!
polkadart-ci  | secp256k1_ecdsa: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | smoldot:
polkadart-ci  | 00:00 +0: loading test/client_basic_test.dart
polkadart-ci  | 00:00 +0: test/client_basic_test.dart: SmoldotClient Basic Tests should initialize client
polkadart-ci  | 00:00 +1: test/client_basic_test.dart: SmoldotClient Basic Tests should fail to initialize twice
polkadart-ci  | 00:00 +2: test/client_basic_test.dart: SmoldotClient Basic Tests should create and add chain with Westend spec
polkadart-ci  | ✓ Chain created with ID: 1
polkadart-ci  | ✓ Successfully loaded Westend chain spec
polkadart-ci  | 00:00 +3: loading test/ffi_basic_test.dart
polkadart-ci  | 00:00 +3: test/ffi_basic_test.dart: FFI Basic Tests should load library and get version
polkadart-ci  | Smoldot FFI version: 0.1.0
polkadart-ci  | 00:00 +4: test/ffi_basic_test.dart: FFI Basic Tests should initialize client with config
polkadart-ci  | Client initialized with handle: 4
polkadart-ci  | 00:00 +5: loading test/chain_info_test.dart
polkadart-ci  | 00:00 +5: test/chain_info_test.dart: Chain Info Tests (setUpAll)
polkadart-ci  | 00:00 +5: test/chain_info_test.dart: Chain Info Tests should get chain info
polkadart-ci  | Chain Info:
polkadart-ci  |   Name: Westend
polkadart-ci  |   Status: ChainStatus.syncing
polkadart-ci  |   Peers: 0
polkadart-ci  |   Block: 15543919
polkadart-ci  |   Hash: 0xefcd8be92e06e6b8d888b3060fdc3443c52e243f5ae9bd8dbe0d548f556edebd
polkadart-ci  | 00:11 +6: test/chain_info_test.dart: Chain Info Tests should get best block number
polkadart-ci  | Best block number: 15543919
polkadart-ci  | 00:11 +7: test/chain_info_test.dart: Chain Info Tests should get best block hash
polkadart-ci  | Best block hash: 0xefcd8be92e06e6b8d888b3060fdc3443c52e243f5ae9bd8dbe0d548f556edebd
polkadart-ci  | 00:11 +8: test/chain_info_test.dart: Chain Info Tests should get peer count
polkadart-ci  | Peer count: 3
polkadart-ci  | 00:11 +9: test/chain_info_test.dart: Chain Info Tests should get chain status
polkadart-ci  | Chain status: ChainStatus.syncing
polkadart-ci  | 00:11 +10: test/chain_info_test.dart: Chain Info Tests should handle multiple concurrent chain info requests
polkadart-ci  | Concurrent requests completed successfully
polkadart-ci  | 00:11 +11: test/chain_info_test.dart: Chain Info Tests (tearDownAll)
polkadart-ci  | 00:11 +11: loading test/smoldot_test.dart
polkadart-ci  | 00:12 +11: test/smoldot_test.dart: SmoldotConfig creates default config
polkadart-ci  | 00:12 +12: test/smoldot_test.dart: SmoldotConfig creates custom config
polkadart-ci  | 00:12 +13: test/smoldot_test.dart: SmoldotConfig converts to JSON
polkadart-ci  | 00:12 +14: test/smoldot_test.dart: AddChainConfig creates config with required fields
polkadart-ci  | 00:12 +15: test/smoldot_test.dart: AddChainConfig creates config with all fields
polkadart-ci  | 00:12 +16: test/smoldot_test.dart: AddChainConfig converts to JSON
polkadart-ci  | 00:12 +17: test/smoldot_test.dart: JsonRpcResponse creates successful response
polkadart-ci  | 00:12 +18: test/smoldot_test.dart: JsonRpcResponse creates error response
polkadart-ci  | 00:12 +19: test/smoldot_test.dart: JsonRpcResponse parses from JSON
polkadart-ci  | 00:12 +20: test/smoldot_test.dart: JsonRpcResponse parses error from JSON
polkadart-ci  | 00:12 +21: test/smoldot_test.dart: JsonRpcError creates error
polkadart-ci  | 00:12 +22: test/smoldot_test.dart: JsonRpcError converts to JSON
polkadart-ci  | 00:12 +23: test/smoldot_test.dart: JsonRpcError formats toString
polkadart-ci  | 00:12 +24: test/smoldot_test.dart: ChainInfo creates chain info
polkadart-ci  | 00:12 +25: test/smoldot_test.dart: ChainInfo converts to JSON
polkadart-ci  | 00:12 +26: test/smoldot_test.dart: LogLevel has correct values
polkadart-ci  | 00:12 +27: test/smoldot_test.dart: LogMessage parses from JSON
polkadart-ci  | 00:12 +28: test/smoldot_test.dart: LogMessage formats toString
polkadart-ci  | 00:12 +29: test/smoldot_test.dart: Exceptions SmoldotException formats message
polkadart-ci  | 00:12 +30: test/smoldot_test.dart: Exceptions ChainException includes chain ID
polkadart-ci  | 00:12 +31: test/smoldot_test.dart: Exceptions JsonRpcException includes error
polkadart-ci  | 00:12 +32: test/smoldot_test.dart: SmoldotPlatform platform is supported
polkadart-ci  | 00:12 +33: test/smoldot_test.dart: SmoldotPlatform has valid library extension
polkadart-ci  | 00:12 +34: test/smoldot_test.dart: SmoldotPlatform has valid full library name
polkadart-ci  | 00:12 +35: test/smoldot_test.dart: SmoldotClient cannot call operations before initialization
polkadart-ci  | 00:12 +36: loading test/subscription_test.dart
polkadart-ci  | 00:12 +36: test/subscription_test.dart: Subscription Tests (setUpAll)
polkadart-ci  | 00:12 +36: test/subscription_test.dart: Subscription Tests should subscribe to new heads
polkadart-ci  | New block: {parentHash: 0x8488d9978468fad24fc036a62b3650bf74b93847e04bde90943b3e7ef4a07bd6, extrinsicsRoot: 0x7f851d6b4efa2125344753468e701475dfe9288a55c4ab594da158fe364eed2b, stateRoot: 0x63e451f6e2f5b835c936972b19977b0d3e6b5e474f302951bb31e1b2137aac75, number: 0xed2e6f, digest: {logs: [0x0642414245b501030d000000d096b61000000000ea4df231da3a45a502c1cbc3c7bd851f524d6b13a7b790c72beb11dadd0e4c35ed8b4d3d447d3bb401dd82b6b207882c346683d2faf916a992178cfcc852eb04a30911db043df4a4d9e29d9c789dcec84403252356e16c599308290e17cbf703, 0x054241424501017665ba1b0138fc8ed27768c22687beb2ea66b63f592a198c7c1f029ca6a2c33d299bf71afeb2193ec8cc9da742b34af34c81605308a490a8bfef13c1a89e6081]}}
polkadart-ci  | Received 1 block notifications
polkadart-ci  | 00:42 +37: test/subscription_test.dart: Subscription Tests should subscribe to finalized heads
polkadart-ci  | Finalized block: {parentHash: 0x8488d9978468fad24fc036a62b3650bf74b93847e04bde90943b3e7ef4a07bd6, extrinsicsRoot: 0x7f851d6b4efa2125344753468e701475dfe9288a55c4ab594da158fe364eed2b, stateRoot: 0x63e451f6e2f5b835c936972b19977b0d3e6b5e474f302951bb31e1b2137aac75, number: 0xed2e6f, digest: {logs: [0x0642414245b501030d000000d096b61000000000ea4df231da3a45a502c1cbc3c7bd851f524d6b13a7b790c72beb11dadd0e4c35ed8b4d3d447d3bb401dd82b6b207882c346683d2faf916a992178cfcc852eb04a30911db043df4a4d9e29d9c789dcec84403252356e16c599308290e17cbf703, 0x054241424501017665ba1b0138fc8ed27768c22687beb2ea66b63f592a198c7c1f029ca6a2c33d299bf71afeb2193ec8cc9da742b34af34c81605308a490a8bfef13c1a89e6081]}}
polkadart-ci  | Received 1 finalized block notifications
polkadart-ci  | 00:42 +38: test/subscription_test.dart: Subscription Tests should handle multiple concurrent subscriptions
polkadart-ci  | Subscription 1 received 1 blocks, Subscription 2 received 1 blocks
polkadart-ci  | 00:42 +39: test/subscription_test.dart: Subscription Tests (tearDownAll)
polkadart-ci  | 00:42 +39: loading test/json_rpc_test.dart
polkadart-ci  | 00:42 +39: test/json_rpc_test.dart: JSON-RPC Tests (setUpAll)
polkadart-ci  | 00:43 +39: test/json_rpc_test.dart: JSON-RPC Tests should make system_chain request
polkadart-ci  | 00:43 +40: test/json_rpc_test.dart: JSON-RPC Tests should make system_version request
polkadart-ci  | 00:43 +41: test/json_rpc_test.dart: JSON-RPC Tests should make system_name request
polkadart-ci  | 00:43 +42: test/json_rpc_test.dart: JSON-RPC Tests should make system_properties request
polkadart-ci  | 00:43 +43: test/json_rpc_test.dart: JSON-RPC Tests should make chain_getFinalizedHead request
polkadart-ci  | 00:53 +44: test/json_rpc_test.dart: JSON-RPC Tests should handle multiple concurrent requests
polkadart-ci  | 00:53 +45: test/json_rpc_test.dart: JSON-RPC Tests should handle request with parameters
polkadart-ci  | 00:53 +46: test/json_rpc_test.dart: JSON-RPC Tests (tearDownAll)
polkadart-ci  | 00:54 +46: All tests passed!
polkadart-ci  | smoldot: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | sr25519:
polkadart-ci  | 00:00 +0: loading test/signature_test.dart
polkadart-ci  | 00:00 +0: test/signature_test.dart: Test Sign and Verify
polkadart-ci  | 00:03 +1: test/signature_test.dart: Test Sign and Verify Keypair
polkadart-ci  | 00:03 +2: test/signature_test.dart: Test Verify
polkadart-ci  | 00:04 +3: test/signature_test.dart: Test Verify Keypair
polkadart-ci  | 00:04 +4: test/signature_test.dart: Test Signature Encode and Decode
polkadart-ci  | 00:04 +5: test/signature_test.dart: Test verify rust
polkadart-ci  | 00:04 +6: test/signature_test.dart: Test verify public key at infinity
polkadart-ci  | 00:04 +7: test/signature_test.dart: Test verify rust preaudit deprecated
polkadart-ci  | 00:05 +8: loading test/batch_test.dart
polkadart-ci  | 00:05 +8: test/batch_test.dart: Verify Batch
polkadart-ci  | 00:13 +9: test/batch_test.dart: Use BatchVerifier() to verify batch
polkadart-ci  | 00:19 +10: test/batch_test.dart: Test Batch Verified Failing cases.
polkadart-ci  | 00:25 +11: loading test/keys_test.dart
polkadart-ci  | 00:25 +11: test/keys_test.dart: Test MiniSecretKey fromHex
polkadart-ci  | 00:28 +12: test/keys_test.dart: Test Generate Keypair
polkadart-ci  | 00:28 +13: test/keys_test.dart: Test Generate Keypair From SecretKey
polkadart-ci  | 00:28 +14: test/keys_test.dart: Test MiniSecret Key_ExpandEd25519
polkadart-ci  | 00:28 +15: test/keys_test.dart: Test MiniSecretKey_Public
polkadart-ci  | 00:28 +16: test/keys_test.dart: Test PublicKey_Decode
polkadart-ci  | 00:28 +17: test/keys_test.dart: Test New Public Key
polkadart-ci  | 00:28 +18: test/keys_test.dart: Test New Secret Key From Ed25519Bytes
polkadart-ci  | 00:29 +19: loading test/derive_test.dart
polkadart-ci  | 00:29 +19: test/derive_test.dart: Test Derive Key
polkadart-ci  | 00:31 +20: test/derive_test.dart: Test Derive Public And Private Match
polkadart-ci  | 00:32 +21: test/derive_test.dart: Test Derive Soft
polkadart-ci  | 00:33 +22: test/derive_test.dart: Test Derive Hard
polkadart-ci  | 00:33 +23: loading test/bip39_test.dart
polkadart-ci  | 00:33 +23: test/bip39_test.dart: Test Substrate Bip39
polkadart-ci  | 00:34 +24: loading test/example_test.dart
polkadart-ci  | 00:35 +24: test/example_test.dart: Example Test
polkadart-ci  | 00:38 +25: test/example_test.dart: Example Test2
polkadart-ci  | 00:39 +26: loading test/vrf_test.dart
polkadart-ci  | 00:39 +26: test/vrf_test.dart: Test Keypair Input and Output
polkadart-ci  | 00:44 +27: test/vrf_test.dart: Test Input and Output
polkadart-ci  | 00:45 +28: test/vrf_test.dart: Test Output  Encode and Decode
polkadart-ci  | 00:45 +29: test/vrf_test.dart: Test Proof Encode and Decode
polkadart-ci  | 00:45 +30: test/vrf_test.dart: Test VRF Sign and Verify
polkadart-ci  | 00:47 +31: test/vrf_test.dart: Test VrfVerify rust
polkadart-ci  | 00:47 +32: test/vrf_test.dart: Test VrfInOut  MakeBytes
polkadart-ci  | 00:48 +33: test/vrf_test.dart: Test VrfVerify NotKusama
polkadart-ci  | 00:48 +34: test/vrf_test.dart: Test VRFVerify Public Key at Infinity
polkadart-ci  | 00:49 +35: All tests passed!
polkadart-ci  | sr25519: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | ss58:
polkadart-ci  | 00:00 +0: loading test/registry_test.dart
polkadart-ci  | 00:00 +0: test/registry_test.dart: Should return a Registry instance when default constructor is called with empty list
polkadart-ci  | 00:00 +1: test/registry_test.dart: Should return a Registry instance when default constructor is called
polkadart-ci  | 00:00 +2: test/registry_test.dart: Should throw DuplicatePrefixException when items list has items with same prefix
polkadart-ci  | 00:00 +3: test/registry_test.dart: Should throw DuplicatePrefixException when items list has items with same network
polkadart-ci  | 00:00 +4: test/registry_test.dart: Should return a Registry instance when factory fromMap is called
polkadart-ci  | 00:00 +5: test/registry_test.dart: Should return a correct registry item when getByNetwork is called
polkadart-ci  | 00:00 +6: test/registry_test.dart: Should throw NoEntryForNetworkException when getByNetwork is called with nonexistent network
polkadart-ci  | 00:00 +7: test/registry_test.dart: Should return a correct registry item when getByPrefix is called
polkadart-ci  | 00:00 +8: test/registry_test.dart: Should throw NoEntryForPrefixException when getByPrefix is called with nonexistent prefix
polkadart-ci  | 00:00 +9: test/registry_test.dart: Should return the same registry item when getByPrefix and getByNetwork are called passing kusama values
polkadart-ci  | 00:00 +10: test/registry_test.dart: Should return registry items
polkadart-ci  | 00:00 +11: loading test/comprehensive_test.dart
polkadart-ci  | 00:00 +11: test/comprehensive_test.dart: Address.decode() valid addresses with single-byte prefix (0-63) should decode Polkadot address (prefix 0)
polkadart-ci  | 00:00 +12: test/comprehensive_test.dart: Address.decode() valid addresses with single-byte prefix (0-63) should decode Kusama address (prefix 2)
polkadart-ci  | 00:00 +13: test/comprehensive_test.dart: Address.decode() valid addresses with single-byte prefix (0-63) should decode Substrate address (prefix 42)
polkadart-ci  | 00:00 +14: test/comprehensive_test.dart: Address.decode() valid addresses with single-byte prefix (0-63) should decode address with prefix 63 (boundary)
polkadart-ci  | 00:00 +15: test/comprehensive_test.dart: Address.decode() valid addresses with two-byte prefix (64-16383) should decode Crust address (prefix 66)
polkadart-ci  | 00:00 +16: test/comprehensive_test.dart: Address.decode() valid addresses with two-byte prefix (64-16383) should decode address with prefix 64 (first two-byte prefix)
polkadart-ci  | 00:00 +17: test/comprehensive_test.dart: Address.decode() valid addresses with two-byte prefix (64-16383) should decode address with prefix 127
polkadart-ci  | 00:00 +18: test/comprehensive_test.dart: Address.decode() valid addresses with two-byte prefix (64-16383) should decode address with prefix 128
polkadart-ci  | 00:00 +19: test/comprehensive_test.dart: Address.decode() valid addresses with two-byte prefix (64-16383) should decode address with prefix 16383 (maximum)
polkadart-ci  | 00:00 +20: test/comprehensive_test.dart: Address.decode() valid pubkey lengths should decode 32-byte pubkey (standard)
polkadart-ci  | 00:00 +21: test/comprehensive_test.dart: Address.decode() valid pubkey lengths should decode 33-byte pubkey (compressed)
polkadart-ci  | 00:00 +22: test/comprehensive_test.dart: Address.decode() valid pubkey lengths should decode 1-byte pubkey
polkadart-ci  | 00:00 +23: test/comprehensive_test.dart: Address.decode() valid pubkey lengths should decode 2-byte pubkey
polkadart-ci  | 00:00 +24: test/comprehensive_test.dart: Address.decode() valid pubkey lengths should decode 4-byte pubkey
polkadart-ci  | 00:00 +25: test/comprehensive_test.dart: Address.decode() valid pubkey lengths should decode 8-byte pubkey
polkadart-ci  | 00:00 +26: test/comprehensive_test.dart: Address.decode() invalid inputs should throw BadAddressLengthException for empty string
polkadart-ci  | 00:00 +27: test/comprehensive_test.dart: Address.decode() invalid inputs should throw BadAddressLengthException for too short address
polkadart-ci  | 00:00 +28: test/comprehensive_test.dart: Address.decode() invalid inputs should throw InvalidPrefixException for invalid first byte (>127)
polkadart-ci  | 00:00 +29: test/comprehensive_test.dart: Address.decode() invalid inputs should throw InvalidCheckSumException for corrupted address
polkadart-ci  | 00:00 +30: test/comprehensive_test.dart: Address.decode() invalid inputs should throw BadAddressLengthException for invalid pubkey length
polkadart-ci  | 00:00 +31: test/comprehensive_test.dart: Address.tryDecode() should return Address for valid address
polkadart-ci  | 00:00 +32: test/comprehensive_test.dart: Address.tryDecode() should return null for empty string
polkadart-ci  | 00:00 +33: test/comprehensive_test.dart: Address.tryDecode() should return null for invalid address
polkadart-ci  | 00:00 +34: test/comprehensive_test.dart: Address.tryDecode() should return null for corrupted checksum
polkadart-ci  | 00:00 +35: test/comprehensive_test.dart: Address.tryDecode() should return null for too short address
polkadart-ci  | 00:00 +36: test/comprehensive_test.dart: Address.encode() valid pubkey lengths should encode 1-byte pubkey
polkadart-ci  | 00:00 +37: test/comprehensive_test.dart: Address.encode() valid pubkey lengths should encode 2-byte pubkey
polkadart-ci  | 00:00 +38: test/comprehensive_test.dart: Address.encode() valid pubkey lengths should encode 4-byte pubkey
polkadart-ci  | 00:00 +39: test/comprehensive_test.dart: Address.encode() valid pubkey lengths should encode 8-byte pubkey
polkadart-ci  | 00:00 +40: test/comprehensive_test.dart: Address.encode() valid pubkey lengths should encode 32-byte pubkey
polkadart-ci  | 00:00 +41: test/comprehensive_test.dart: Address.encode() valid pubkey lengths should encode 33-byte pubkey
polkadart-ci  | 00:00 +42: test/comprehensive_test.dart: Address.encode() prefix ranges should encode with prefix 0
polkadart-ci  | 00:00 +43: test/comprehensive_test.dart: Address.encode() prefix ranges should encode with prefix 63 (last single-byte)
polkadart-ci  | 00:00 +44: test/comprehensive_test.dart: Address.encode() prefix ranges should encode with prefix 64 (first two-byte)
polkadart-ci  | 00:00 +45: test/comprehensive_test.dart: Address.encode() prefix ranges should encode with prefix 16383 (maximum)
polkadart-ci  | 00:00 +46: test/comprehensive_test.dart: Address.encode() roundtrip encode/decode should roundtrip Substrate address
polkadart-ci  | 00:00 +47: test/comprehensive_test.dart: Address.encode() roundtrip encode/decode should roundtrip Polkadot address
polkadart-ci  | 00:00 +48: test/comprehensive_test.dart: Address.encode() roundtrip encode/decode should roundtrip Kusama address
polkadart-ci  | 00:00 +49: test/comprehensive_test.dart: Address.encode() custom prefix override should encode with custom prefix parameter
polkadart-ci  | 00:00 +50: test/comprehensive_test.dart: Address.encode() invalid inputs should throw InvalidPrefixException for negative prefix
polkadart-ci  | 00:00 +51: test/comprehensive_test.dart: Address.encode() invalid inputs should throw InvalidPrefixException for prefix > 16383
polkadart-ci  | 00:00 +52: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 3-byte pubkey
polkadart-ci  | 00:00 +53: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 5-byte pubkey
polkadart-ci  | 00:00 +54: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 6-byte pubkey
polkadart-ci  | 00:00 +55: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 7-byte pubkey
polkadart-ci  | 00:00 +56: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 9-byte pubkey
polkadart-ci  | 00:00 +57: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 31-byte pubkey
polkadart-ci  | 00:00 +58: test/comprehensive_test.dart: Address.encode() invalid inputs should throw BadAddressLengthException for 35-byte pubkey
polkadart-ci  | 00:00 +59: test/comprehensive_test.dart: Address.withPrefix() should create new address with different prefix
polkadart-ci  | 00:00 +60: test/comprehensive_test.dart: Address.withPrefix() should throw InvalidPrefixException for negative prefix
polkadart-ci  | 00:00 +61: test/comprehensive_test.dart: Address.withPrefix() should throw InvalidPrefixException for prefix > 16383
polkadart-ci  | 00:00 +62: test/comprehensive_test.dart: Address.withPrefix() should create a copy of pubkey (not reference)
polkadart-ci  | 00:00 +63: test/comprehensive_test.dart: Address.toString() should return formatted string with prefix and hex pubkey
polkadart-ci  | 00:00 +64: test/comprehensive_test.dart: Address equality should be equal when prefix and pubkey match
polkadart-ci  | 00:00 +65: test/comprehensive_test.dart: Address equality should not be equal when prefix differs
polkadart-ci  | 00:00 +66: test/comprehensive_test.dart: Address equality should not be equal when pubkey differs
polkadart-ci  | 00:00 +67: test/comprehensive_test.dart: Address equality props should contain prefix and pubkey
polkadart-ci  | 00:00 +68: test/comprehensive_test.dart: Codec constructor should create Codec with valid prefix
polkadart-ci  | 00:00 +69: test/comprehensive_test.dart: Codec constructor should throw InvalidPrefixException for negative prefix
polkadart-ci  | 00:00 +70: test/comprehensive_test.dart: Codec constructor should throw InvalidPrefixException for prefix > 16383
polkadart-ci  | 00:00 +71: test/comprehensive_test.dart: Codec fromNetwork() should create Codec from valid network name
polkadart-ci  | 00:00 +72: test/comprehensive_test.dart: Codec fromNetwork() should create Codec from polkadot network
polkadart-ci  | 00:00 +73: test/comprehensive_test.dart: Codec fromNetwork() should create Codec from substrate network
polkadart-ci  | 00:00 +74: test/comprehensive_test.dart: Codec fromNetwork() should throw NoEntryForNetworkException for invalid network
polkadart-ci  | 00:00 +75: test/comprehensive_test.dart: Codec encode() should encode bytes to address string
polkadart-ci  | 00:00 +76: test/comprehensive_test.dart: Codec decode() should decode address to bytes
polkadart-ci  | 00:00 +77: test/comprehensive_test.dart: Codec decode() should throw InvalidAddressPrefixException for prefix mismatch
polkadart-ci  | 00:00 +78: test/comprehensive_test.dart: Codec roundtrip should roundtrip encode/decode
polkadart-ci  | 00:00 +79: test/comprehensive_test.dart: Codec registry should have static registry available
polkadart-ci  | 00:00 +80: test/comprehensive_test.dart: Registry constructor should create empty registry
polkadart-ci  | 00:00 +81: test/comprehensive_test.dart: Registry constructor should create registry with items
polkadart-ci  | 00:00 +82: test/comprehensive_test.dart: Registry constructor should throw DuplicatePrefixException for duplicate prefix
polkadart-ci  | 00:00 +83: test/comprehensive_test.dart: Registry constructor should throw DuplicateNetworkException for duplicate network
polkadart-ci  | 00:00 +84: test/comprehensive_test.dart: Registry fromMap() should create registry from JSON list
polkadart-ci  | 00:00 +85: test/comprehensive_test.dart: Registry fromMap() should create registry from actual registry data
polkadart-ci  | 00:00 +86: test/comprehensive_test.dart: Registry getByPrefix() should return item for valid prefix
polkadart-ci  | 00:00 +87: test/comprehensive_test.dart: Registry getByPrefix() should throw NoEntryForPrefixException for invalid prefix
polkadart-ci  | 00:00 +88: test/comprehensive_test.dart: Registry getByNetwork() should return item for valid network
polkadart-ci  | 00:00 +89: test/comprehensive_test.dart: Registry getByNetwork() should throw NoEntryForNetworkException for invalid network
polkadart-ci  | 00:00 +90: test/comprehensive_test.dart: Registry items getter should return copy of items list
polkadart-ci  | 00:00 +91: test/comprehensive_test.dart: RegistryItem constructor should create item with required fields
polkadart-ci  | 00:00 +92: test/comprehensive_test.dart: RegistryItem fromJson() should create item from valid JSON
polkadart-ci  | 00:00 +93: test/comprehensive_test.dart: RegistryItem toJson() should convert to JSON
polkadart-ci  | 00:00 +94: test/comprehensive_test.dart: RegistryItem toJson() should roundtrip fromJson/toJson
polkadart-ci  | 00:00 +95: test/comprehensive_test.dart: RegistryItem equality should be equal when prefix and network match
polkadart-ci  | 00:00 +96: test/comprehensive_test.dart: RegistryItem equality should not be equal when prefix differs
polkadart-ci  | 00:00 +97: test/comprehensive_test.dart: RegistryItem equality should not be equal when network differs
polkadart-ci  | 00:00 +98: test/comprehensive_test.dart: RegistryItem props should have correct props list
polkadart-ci  | 00:00 +99: test/comprehensive_test.dart: Exceptions DuplicatePrefixException should have correct toString
polkadart-ci  | 00:00 +100: test/comprehensive_test.dart: Exceptions DuplicateNetworkException should have correct toString
polkadart-ci  | 00:00 +101: test/comprehensive_test.dart: Exceptions NoEntryForNetworkException should have correct toString
polkadart-ci  | 00:00 +102: test/comprehensive_test.dart: Exceptions NoEntryForPrefixException should have correct toString
polkadart-ci  | 00:00 +103: test/comprehensive_test.dart: Exceptions InvalidAddressPrefixException should have correct toString
polkadart-ci  | 00:00 +104: test/comprehensive_test.dart: Exceptions InvalidPrefixException should have correct toString with prefix
polkadart-ci  | 00:00 +105: test/comprehensive_test.dart: Exceptions InvalidPrefixException should have correct toString without prefix
polkadart-ci  | 00:00 +106: test/comprehensive_test.dart: Exceptions InvalidCheckSumException should have correct toString
polkadart-ci  | 00:00 +107: test/comprehensive_test.dart: Exceptions BadAddressLengthException should have correct toString with address
polkadart-ci  | 00:00 +108: test/comprehensive_test.dart: Exceptions BadAddressLengthException should have correct toString without address
polkadart-ci  | 00:00 +109: test/comprehensive_test.dart: Integration tests real-world addresses should handle Polkadot treasury address
polkadart-ci  | 00:00 +110: test/comprehensive_test.dart: Integration tests real-world addresses should handle multiple Kusama addresses
polkadart-ci  | 00:00 +111: test/comprehensive_test.dart: Integration tests cross-network address conversion should convert Substrate address to Polkadot
polkadart-ci  | 00:00 +112: test/comprehensive_test.dart: Integration tests cross-network address conversion should convert Substrate address to Kusama
polkadart-ci  | 00:00 +113: test/comprehensive_test.dart: Integration tests cross-network address conversion should preserve pubkey when converting between networks
polkadart-ci  | 00:00 +114: test/comprehensive_test.dart: Integration tests registry data integrity should have polkadot at prefix 0
polkadart-ci  | 00:00 +115: test/comprehensive_test.dart: Integration tests registry data integrity should have kusama at prefix 2
polkadart-ci  | 00:00 +116: test/comprehensive_test.dart: Integration tests registry data integrity should have substrate at prefix 42
polkadart-ci  | 00:00 +117: test/comprehensive_test.dart: Integration tests registry data integrity getByPrefix and getByNetwork should return same item
polkadart-ci  | 00:00 +118: test/comprehensive_test.dart: computeHash() should produce consistent hash
polkadart-ci  | 00:00 +119: test/comprehensive_test.dart: computeHash() should produce different hash for different data
polkadart-ci  | 00:01 +120: loading test/ss58_encode_test.dart
polkadart-ci  | 00:01 +120: test/ss58_encode_test.dart: SS58Codec encode method Should encode when prefix is zero
polkadart-ci  | 00:01 +121: test/ss58_encode_test.dart: SS58Codec encode method Should encode when prefix is 64
polkadart-ci  | 00:01 +122: test/ss58_encode_test.dart: SS58Codec encode method Should encode when bytes,length is 8
polkadart-ci  | 00:01 +123: test/ss58_encode_test.dart: SS58Codec encode method Should encode when bytes,length is 32
polkadart-ci  | 00:01 +124: test/ss58_encode_test.dart: SS58Codec encode method Should encode and return correct address
polkadart-ci  | 00:01 +125: test/ss58_encode_test.dart: SS58Codec encode exception Should throw InvalidPrefixException when an address has negative prefix
polkadart-ci  | 00:01 +126: test/ss58_encode_test.dart: SS58Codec encode exception Should throw InvalidPrefixException when an address prefix is greater than the limit
polkadart-ci  | 00:01 +127: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 3.
polkadart-ci  | 00:01 +128: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 5.
polkadart-ci  | 00:01 +129: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 6.
polkadart-ci  | 00:01 +130: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 7.
polkadart-ci  | 00:01 +131: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 9.
polkadart-ci  | 00:01 +132: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 31.
polkadart-ci  | 00:01 +133: test/ss58_encode_test.dart: SS58Codec encode exception Should throw BadAddressLengthException when an address bytes length is equal to 35.
polkadart-ci  | 00:01 +134: loading test/ss58_base_test.dart
polkadart-ci  | 00:01 +134: test/ss58_base_test.dart: Codec decode method tests Should return correct bytes
polkadart-ci  | 00:01 +135: test/ss58_base_test.dart: Codec decode method tests Should throw when given prefix does not match with decoded prefix
polkadart-ci  | 00:01 +136: test/ss58_base_test.dart: Codec encode method tests:  Should return correct address
polkadart-ci  | 00:01 +137: test/ss58_base_test.dart: Codec encode method tests:  Should return correct address when prefix is zero
polkadart-ci  | 00:01 +138: test/ss58_base_test.dart: Codec encode method tests:  Should throw when given prefix is negative
polkadart-ci  | 00:01 +139: test/ss58_base_test.dart: Codec encode method tests:  Should throw when given prefix is greater than 16383
polkadart-ci  | 00:01 +140: test/ss58_base_test.dart: Codec encode method tests:  Should return a Codec instance with defined prefix
polkadart-ci  | 00:01 +141: loading test/ss58_decode_test.dart
polkadart-ci  | 00:01 +141: test/ss58_decode_test.dart: SS58Codec decode method tests Should decoded data be equal to expected address
polkadart-ci  | 00:01 +142: test/ss58_decode_test.dart: SS58Codec decode method tests Should decode the given kusama addresses and return prefix equal to kusama prefix
polkadart-ci  | 00:01 +143: test/ss58_decode_test.dart: SS58Codec decode method tests Should decode the given polkadot address and return prefix equal to polkadot prefix
polkadart-ci  | 00:01 +144: test/ss58_decode_test.dart: SS58Codec decode method tests Should decode the given crust address and return prefix equal to crust prefix
polkadart-ci  | 00:01 +145: test/ss58_decode_test.dart: SS58Codec decode method exception testing should throw BadAddressLengthException when data.lentgh is too small
polkadart-ci  | 00:02 +146: test/ss58_decode_test.dart: SS58Codec decode method exception testing should throw InvalidPrefixException when first character of data is greater than 127
polkadart-ci  | 00:02 +147: test/ss58_decode_test.dart: SS58Codec decode method exception testing Should throw BadAddressLengthException when decoded address (data.length - offset) != any of [2, 3, 5, 9, 34, 35]
polkadart-ci  | 00:02 +148: test/ss58_decode_test.dart: SS58Codec decode method exception testing Should throw InvalidCheckSumException when decoded address is Invalid
polkadart-ci  | 00:02 +149: loading test/registry_item_test.dart
polkadart-ci  | 00:02 +149: test/registry_item_test.dart: Should return one instance of RegistryItem when call fromJson constructor
polkadart-ci  | 00:02 +150: test/registry_item_test.dart: Should return the correct map values when call toJson
polkadart-ci  | 00:02 +151: test/registry_item_test.dart: Should return all props of RegistryItem
polkadart-ci  | 00:02 +152: All tests passed!
polkadart-ci  | ss58: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_bip39:
polkadart-ci  | 00:00 +0: loading test/secret_uri_test.dart
polkadart-ci  | 00:00 +0: test/secret_uri_test.dart: interpret std secret string
polkadart-ci  | 00:00 +1: loading test/substrate_bip39_test.dart
polkadart-ci  | 00:00 +1: test/substrate_bip39_test.dart: vectors are correct
polkadart-ci  | 00:02 +2: test/substrate_bip39_test.dart: seedFromUri
polkadart-ci  | 00:02 +3: test/substrate_bip39_test.dart: seedFromUri
polkadart-ci  | 00:02 +4: test/substrate_bip39_test.dart: miniSecretFromEntropy
polkadart-ci  | 00:02 +5: All tests passed!
polkadart-ci  | substrate_bip39: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | substrate_metadata:
polkadart-ci  | 00:00 +0: loading test/metadata_tests/metadata_v15_test.dart
polkadart-ci  | 00:00 +0: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests (setUpAll)
polkadart-ci  | 00:00 +0: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Basic Decoding Tests Magic number is valid
polkadart-ci  | 00:00 +1: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Basic Decoding Tests Metadata version is 15
polkadart-ci  | 00:00 +2: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Basic Decoding Tests Types are populated
polkadart-ci  | 00:00 +3: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Basic Decoding Tests Pallets are populated
polkadart-ci  | 00:00 +4: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Basic Decoding Tests Runtime APIs are populated
polkadart-ci  | 00:00 +5: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Basic Decoding Tests Outer enums are populated
polkadart-ci  | 00:00 +6: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests V15-Specific Feature Tests Extrinsic metadata uses signed extensions
polkadart-ci  | 00:00 +7: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests V15-Specific Feature Tests Pallets have documentation
polkadart-ci  | 00:00 +8: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests System Pallet Tests System pallet exists
polkadart-ci  | 00:00 +9: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests System Pallet Tests System pallet has constants
polkadart-ci  | 00:00 +10: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests System Pallet Tests System pallet has storage
polkadart-ci  | 00:00 +11: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests System Pallet Tests System pallet has calls
polkadart-ci  | 00:00 +12: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests System Pallet Tests System pallet has events
polkadart-ci  | 00:00 +13: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests System Pallet Tests System pallet has errors
polkadart-ci  | 00:00 +14: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Balances Pallet Tests Balances pallet exists and has constants
polkadart-ci  | 00:00 +15: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Type Resolution Tests Can resolve types by ID
polkadart-ci  | 00:00 +16: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Type Resolution Tests Can look up call type
polkadart-ci  | 00:00 +17: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Type Resolution Tests Can look up event type
polkadart-ci  | 00:00 +18: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests MetadataTypeRegistry Tests Registry builds successfully from V15 metadata
polkadart-ci  | 00:00 +19: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests MetadataTypeRegistry Tests Registry has type definitions
polkadart-ci  | 00:00 +20: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Merkleization Tests Can create MetadataMerkleizer from V15 metadata
polkadart-ci  | 00:00 +21: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Merkleization Tests Can compute metadata digest
polkadart-ci  | 00:00 +22: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Merkleization Tests Digest is deterministic
polkadart-ci  | 00:00 +23: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Merkleization Tests Lookup entries are generated
polkadart-ci  | 00:00 +24: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Merkleization Tests Extrinsic info is correct for V15
polkadart-ci  | 00:00 +25: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Merkleization Tests Extra info contains correct chain data
polkadart-ci  | 00:00 +26: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests JSON Serialization Tests Metadata can be serialized to JSON
polkadart-ci  | 00:00 +27: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests JSON Serialization Tests V15 metadata JSON has expected structure
polkadart-ci  | 00:00 +28: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Round-trip Encoding Tests Metadata can be re-encoded and decoded
polkadart-ci  | 00:00 +29: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Multiple Chain V15 Tests Can decode westend V15 metadata
polkadart-ci  | 00:00 +30: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Multiple Chain V15 Tests Can decode paseo V15 metadata
polkadart-ci  | 00:00 +31: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Multiple Chain V15 Tests Can decode polkadot V15 metadata
polkadart-ci  | 00:00 +32: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests Multiple Chain V15 Tests Can decode kusama V15 metadata
polkadart-ci  | 00:00 +33: test/metadata_tests/metadata_v15_test.dart: Metadata V15 Tests (tearDownAll)
polkadart-ci  | 00:01 +33: loading test/hashers_test.dart
polkadart-ci  | 00:01 +33: test/hashers_test.dart: Storage Hashers Test Blake2bHasher works
polkadart-ci  | 00:01 +34: test/hashers_test.dart: Storage Hashers Test TwoxxHasher works
polkadart-ci  | 00:01 +35: test/hashers_test.dart: Storage Hashers Test TwoxxHasher works
polkadart-ci  | 00:01 +36: test/hashers_test.dart: Storage Hashers Test TwoxxHasher with 32-byte AccountId
polkadart-ci  | 00:01 +37: loading test/metadata/metadata_decode_test.dart
polkadart-ci  | 00:01 +37: test/metadata/metadata_decode_test.dart: (setUpAll)
polkadart-ci  | 00:02 +37: test/metadata/metadata_decode_test.dart: Metadata merkleize tests: digests
polkadart-ci  | 00:02 +38: test/metadata/metadata_decode_test.dart: Metadata merkleize tests: generates proofs for extrinsics
polkadart-ci  | 00:02 +39: test/metadata/metadata_decode_test.dart: Metadata merkleize tests: generates proofs for extrinsics parts
polkadart-ci  | 00:02 +40: test/metadata/metadata_decode_test.dart: Metadata merkleize tests: generates proofs for extrinsic payload
polkadart-ci  | 00:02 +41: test/metadata/metadata_decode_test.dart: Metadata merkleize tests: fails to create with wrong extra info
polkadart-ci  | 00:02 +42: test/metadata/metadata_decode_test.dart: (tearDownAll)
polkadart-ci  | 00:02 +42: loading test/metadata/metadata_json_conversion_test.dart
polkadart-ci  | 00:02 +42: test/metadata/metadata_json_conversion_test.dart: Metadata Encode Decode Test: Decode/Encode version v14
polkadart-ci  | 00:02 +43: test/metadata/metadata_json_conversion_test.dart: Metadata Encode Decode Test: Decode/Encode version v15
polkadart-ci  | 00:03 +44: loading test/polkadot_v14_tests/constants_test.dart
polkadart-ci  | 00:03 +44: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Snapshot Comparison Test - Decode matches saved snapshot
polkadart-ci  | 00:03 +45: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Decode All Constants Test
polkadart-ci  | 00:03 +46: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Decode Specific Pallet Constants - System
polkadart-ci  | 00:03 +47: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Decode Specific Pallet Constants - Balances
polkadart-ci  | 00:03 +48: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Decode Specific Pallet Constants - Timestamp
polkadart-ci  | 00:03 +49: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  ConstantInfo toJson() Serialization Test
polkadart-ci  | 00:03 +50: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Verify Constant Metadata - getConstantInfo
polkadart-ci  | 00:03 +51: test/polkadot_v14_tests/constants_test.dart: Constants Decode Tests:  Verify All Pallets Have Constants Accessible
polkadart-ci  | 00:04 +52: loading test/polkadot_v14_tests/extrinsics_test.dart
polkadart-ci  | 00:04 +52: test/polkadot_v14_tests/extrinsics_test.dart: Extrinsics Decode/Encode:  Decode Test
polkadart-ci  | 00:04 +53: test/polkadot_v14_tests/extrinsics_test.dart: Extrinsics Decode/Encode:  Encode Test
polkadart-ci  | 00:04 +54: test/polkadot_v14_tests/extrinsics_test.dart: Extrinsics Decode/Encode:  Round-Trip Test (Decode First)
polkadart-ci  | 00:04 +55: test/polkadot_v14_tests/extrinsics_test.dart: Extrinsics Decode/Encode:  Round-Trip Test (Encode First)
polkadart-ci  | 00:04 +56: loading test/polkadot_v14_tests/events_test.dart
polkadart-ci  | 00:04 +56: test/polkadot_v14_tests/events_test.dart: Events Decode/Encode:  Decode Test
polkadart-ci  | 00:05 +57: test/polkadot_v14_tests/events_test.dart: Events Decode/Encode:  Encode Test
polkadart-ci  | 00:05 +58: test/polkadot_v14_tests/events_test.dart: Events Decode/Encode:  Round-Trip Test (Decode First)
polkadart-ci  | 00:05 +59: test/polkadot_v14_tests/events_test.dart: Events Decode/Encode:  Round-Trip Test (Encode First)
polkadart-ci  | 00:05 +60: loading test/era_extrinsic_test.dart
polkadart-ci  | 00:05 +60: test/era_extrinsic_test.dart: Placeholder test
polkadart-ci  | 00:05 +61: All tests passed!
polkadart-ci  | substrate_metadata: SUCCESS
polkadart-ci  | --------------------------------------------------------------------------------
polkadart-ci  | 
polkadart-ci  | $ melos exec
polkadart-ci  |   └> dart test --no-chain-stack-traces --ignore-timeouts --coverage="coverage" --concurrency=1 --exclude-tags=chain
polkadart-ci  |      └> SUCCESS
polkadart-ci  | melos run test:chain
polkadart-ci  |   └> dart test packages/substrate_metadata/test/chain_tests/ --no-chain-stack-traces --concurrency=1
polkadart-ci  |      └> RUNNING
polkadart-ci  | 
polkadart-ci  | 00:00 +0: loading packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart
polkadart-ci  | Warning: A tag was used that wasn't specified in dart_test.yaml.
polkadart-ci  |   chain was used in the suite itself
polkadart-ci  | 
polkadart-ci  | 00:00 +0: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: Polkadot V14 Block Headers - Required Fields block 7500000
polkadart-ci  | 00:00 +1: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: Polkadot V14 Block Headers - Required Fields block 7500001
polkadart-ci  | 00:00 +2: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: Polkadot V14 Block Headers - Required Fields block 7500002...
polkadart-ci  | 00:01 +793: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: Polkadot V14 Block Headers - Digest Logs block 29088549
polkadart-ci  | 00:01 +794: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: Polkadot V14 Block Headers - Digest Logs block 29088589
polkadart-ci  | 00:01 +795: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: Polkadot V14 Block Headers - Digest Logs block 29088599
polkadart-ci  | 00:01 +796: packages/substrate_metadata/test/chain_tests/polkadot/v14/block_headers_test.dart: block numbers are in ascending order
polkadart-ci  | 00:01 +797: loading packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart
polkadart-ci  | Warning: A tag was used that wasn't specified in dart_test.yaml.
polkadart-ci  |   chain was used in the suite itself
polkadart-ci  | 
polkadart-ci  | 00:02 +797: packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart: Polkadot V14 Extrinsics - Decode block 7500001
polkadart-ci  | 00:02 +798: packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart: Polkadot V14 Extrinsics - Decode block 7500002
polkadart-ci  | 00:02 +799: packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart: Polkadot V14 Extrinsics - Decode block 7503562
...
polkadart-ci  | 00:05 +1128: packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart: Polkadot V14 Extrinsics - Round-trip block 23341244
polkadart-ci  | 00:05 +1129: packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart: Polkadot V14 Extrinsics - Round-trip block 24756109
polkadart-ci  | 00:05 +1130: packages/substrate_metadata/test/chain_tests/polkadot/v14/extrinsics_test.dart: Polkadot V14 Extrinsics - Round-trip block 25005482
polkadart-ci  | 00:05 +1131: loading packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart
polkadart-ci  | Warning: A tag was used that wasn't specified in dart_test.yaml.
polkadart-ci  |   chain was used in the suite itself
polkadart-ci  | 
polkadart-ci  | 00:05 +1131: packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart: Polkadot V14 Events - Decode block 7500001
polkadart-ci  | 00:05 +1132: packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart: Polkadot V14 Events - Decode block 7500002
polkadart-ci  | 00:05 +1133: packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart: Polkadot V14 Events - Decode block 7503562
...
polkadart-ci  | 00:08 +1519: packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart: Polkadot V14 Events - Round-trip block 28042760
polkadart-ci  | 00:08 +1520: packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart: Polkadot V14 Events - Round-trip block 28488805
polkadart-ci  | 00:08 +1521: packages/substrate_metadata/test/chain_tests/polkadot/v14/events_test.dart: Polkadot V14 Events - Round-trip block 28806555
polkadart-ci  | 00:08 +1522: loading packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart
polkadart-ci  | Warning: A tag was used that wasn't specified in dart_test.yaml.
polkadart-ci  |   chain was used in the suite itself
polkadart-ci  | 
polkadart-ci  | 00:09 +1522: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: Kusama V14 Block Headers - Required Fields block 9625129
polkadart-ci  | 00:09 +1523: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: Kusama V14 Block Headers - Required Fields block 9625130
polkadart-ci  | 00:09 +1524: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: Kusama V14 Block Headers - Required Fields block 9625131
...
polkadart-ci  | 00:10 +2369: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: Kusama V14 Block Headers - Digest Logs block 31410529
polkadart-ci  | 00:10 +2370: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: Kusama V14 Block Headers - Digest Logs block 31410569
polkadart-ci  | 00:10 +2371: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: Kusama V14 Block Headers - Digest Logs block 31410579
polkadart-ci  | 00:10 +2372: packages/substrate_metadata/test/chain_tests/kusama/v14/block_headers_test.dart: block numbers are in ascending order
polkadart-ci  | 00:10 +2373: loading packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart
polkadart-ci  | Warning: A tag was used that wasn't specified in dart_test.yaml.
polkadart-ci  |   chain was used in the suite itself
polkadart-ci  | 
polkadart-ci  | 00:11 +2373: packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart: Kusama V14 Extrinsics - Decode block 9625130
polkadart-ci  | 00:11 +2374: packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart: Kusama V14 Extrinsics - Decode block 9625131
polkadart-ci  | 00:11 +2375: packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart: Kusama V14 Extrinsics - Decode block 9639322
...
polkadart-ci  | 00:14 +2730: packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart: Kusama V14 Extrinsics - Round-trip block 24786389
polkadart-ci  | 00:14 +2731: packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart: Kusama V14 Extrinsics - Round-trip block 27155297
polkadart-ci  | 00:14 +2732: packages/substrate_metadata/test/chain_tests/kusama/v14/extrinsics_test.dart: Kusama V14 Extrinsics - Round-trip block 27287736
polkadart-ci  | 00:14 +2733: loading packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart
polkadart-ci  | Warning: A tag was used that wasn't specified in dart_test.yaml.
polkadart-ci  |   chain was used in the suite itself
polkadart-ci  | 
polkadart-ci  | 00:14 +2733: packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart: Kusama V14 Events - Decode block 9625130
polkadart-ci  | 00:14 +2734: packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart: Kusama V14 Events - Decode block 9625131
polkadart-ci  | 00:14 +2735: packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart: Kusama V14 Events - Decode block 9639322
...
polkadart-ci  | 00:17 +3148: packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart: Kusama V14 Events - Round-trip block 30296842
polkadart-ci  | 00:17 +3149: packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart: Kusama V14 Events - Round-trip block 30552008
polkadart-ci  | 00:17 +3150: packages/substrate_metadata/test/chain_tests/kusama/v14/events_test.dart: Kusama V14 Events - Round-trip block 31410079
polkadart-ci  | 00:17 +3151: All tests passed!
[Kpolkadart-ci exited with code 0
```