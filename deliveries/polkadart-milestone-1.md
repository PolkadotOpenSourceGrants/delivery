# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadart.md
* **Milestone Number:** 1

**Context**   

This milestone focuses on the implementation of **typed metadata support** across all Polkadart packages. This represents a major rewrite of the core packages to leverage the full power of Substrate's metadata V14 and V15, enabling type-safe extrinsic construction, event decoding, and storage queries.

The key achievements include:
- **substrate_metadata v2.0.0**: Complete rewrite with `MetadataTypeRegistry`, typed codecs for events/extrinsics/constants, and built-in storage hashers
- **polkadart major update**: New fluent `ExtrinsicBuilder` API, automatic signed extension handling, `Balances` module, and `ChainDataFetcher`
- **polkadart_cli updates**: CLI adjusted to work seamlessly with the new typed metadata system

### Packages Updated

All packages have been updated and are published on [pub.dev](https://pub.dev/publishers/polkadart.dev/packages):

- [polkadart](https://pub.dev/packages/polkadart)
- [polkadart_cli](https://pub.dev/packages/polkadart_cli)
- [polkadart_keyring](https://pub.dev/packages/polkadart_keyring)
- [polkadart_scale_codec](https://pub.dev/packages/polkadart_scale_codec)
- [substrate_metadata](https://pub.dev/packages/substrate_metadata)
- [sr25519](https://pub.dev/packages/sr25519)
- [secp256k1_ecdsa](https://pub.dev/packages/secp256k1_ecdsa)
- [ss58](https://pub.dev/packages/ss58)
- [substrate_bip39](https://pub.dev/packages/substrate_bip39)
- [ink_abi](https://pub.dev/packages/ink_abi)
- [ink_cli](https://pub.dev/packages/ink_cli)

**Deliverables**

| Number | Deliverable | Link | Notes |
| -----: | ----------- | ---- | ----- |
| 0a.    | License            | [Apache 2.0](https://github.com/justkawal/polkadart/blob/main/LICENSE) | All packages use Apache 2.0 license |
| 0b.    | Documentation      | [polkadart.dev](https://polkadart.dev) / [substrate_metadata README](https://github.com/justkawal/polkadart/tree/main/packages/substrate_metadata) / [polkadart README](https://github.com/justkawal/polkadart/tree/main/packages/polkadart) / [polkadart_cli README](https://github.com/justkawal/polkadart/tree/main/packages/polkadart_cli) | Complete documentation for the packages |
| 0c.    | Testing            | [substrate_metadata tests](https://github.com/justkawal/polkadart/tree/main/packages/substrate_metadata/test) / [polkadart tests](https://github.com/justkawal/polkadart/tree/main/packages/polkadart/test) / [polkadart_cli tests](https://github.com/justkawal/polkadart/tree/main/packages/polkadart_cli/test) | Unit tests for all main functionalities |
| 0d.    | Docker             | [Dockerfile](https://github.com/justkawal/polkadart/blob/main/Dockerfile) / [docker-compose.yml](https://github.com/justkawal/polkadart/blob/main/docker-compose.yml) | Run `docker compose up` to execute all tests |
| 0e.    | Article            | [Article](https://hackmd.io/@leonardocustodio/polkadart-typed-metadata) | Article explaining the new typed metadata features |
| 1.     | Substrate Metadata | [substrate_metadata package](https://github.com/justkawal/polkadart/tree/main/packages/substrate_metadata) | Major v2.0.0 rewrite: `MetadataTypeRegistry` for typed codec generation, `ChainInfo` facade, `EventsRecordCodec`, `ExtrinsicsCodec`, `ConstantsCodec` with lazy loading, built-in storage hashers (Blake2b, TwoXX), V14 & V15 support only |
| 2.     | Registry           | [MetadataTypeRegistry](https://github.com/justkawal/polkadart/blob/main/packages/substrate_metadata/lib/registry/metadata_type_registry.dart) | Core type resolution engine that builds typed codecs from runtime metadata, enabling automatic adaptation to any Substrate chain and runtime upgrades |
| 3.     | Polkadart CLI      | [polkadart_cli package](https://github.com/justkawal/polkadart/tree/main/packages/polkadart_cli) | CLI generates typed Dart classes from chain metadata, adjusted to work seamlessly with the new typed metadata system |
| 4.     | Polkadart          | [polkadart package](https://github.com/justkawal/polkadart/tree/main/packages/polkadart) | Major rewrite: Fluent `ExtrinsicBuilder` API, automatic signed extension handling via `ExtensionBuilder`, new `Balances` module, `ChainDataFetcher` for parallel data fetching, redesigned `Multisig` API with the new typed base metadata |

**Additional Information**

### Key Architectural Changes

**substrate_metadata v2.0.0:**
- `MetadataTypeRegistry`: Core type resolution engine that dynamically builds codecs from runtime metadata
- `ChainInfo`: High-level facade providing access to `eventsCodec`, `extrinsicsCodec`, `constantsCodec`, and `callsCodec`
- `RuntimeMetadataPrefixed`: Direct parsing of V14/V15 metadata with `buildChainInfo()` factory
- Strongly typed models: `RuntimeEvent`, `UncheckedExtrinsic`, `RuntimeCall`, `EventRecord`
- Removed: Legacy V9-V13 support, `Chain` class, `MetadataDecoder` singleton, `LegacyTypes`

**polkadart major update:**
- `ExtrinsicBuilder`: Fluent API for building extrinsics with `quickSend()`, `fromChainData()`, and manual construction
- `ExtensionBuilder`: Automatic signed extension handling (replaces `SubstrateSignedExtensions`)
- `Balances` module: Type-safe calls for `transfer`, `transferKeepAlive`, `transferAll`, `forceTransfer`, `forceSetBalance`
- `ChainDataFetcher`: Parallel fetching of genesis hash, block info, runtime version, and nonce
- `MultisigAccount` and `Multisig`: Redesigned instance-based multisig API
- Storage classes moved to `substrate_metadata` package

### Documentation & Examples

Comprehensive documentation is available at:
- https://polkadart.dev - Main documentation website
- https://github.com/justkawal/polkadart/tree/main/packages/polkadart
- https://github.com/justkawal/polkadart/tree/main/packages/polkadart_cli
- https://github.com/justkawal/polkadart/tree/main/packages/polkadart_keyring
- https://github.com/justkawal/polkadart/tree/main/packages/polkadart_scale_codec
- https://github.com/justkawal/polkadart/tree/main/packages/substrate_metadata
- https://github.com/justkawal/polkadart/tree/main/packages/sr25519
- https://github.com/justkawal/polkadart/tree/main/packages/secp256k1_ecdsa
- https://github.com/justkawal/polkadart/tree/main/packages/ss58
- https://github.com/justkawal/polkadart/tree/main/packages/substrate_bip39
- https://github.com/justkawal/polkadart/tree/main/packages/ink_abi
- https://github.com/justkawal/polkadart/tree/main/packages/ink_cli

### Running Tests

To run all unit tests using Docker:

```bash
git clone https://github.com/justkawal/polkadart
cd polkadart
docker build -t polkadart .
docker run --rm polkadart
```
