# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**

* **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadart.md
* **Milestone Number:** 2

**Context**

This milestone adds **Metadata V16 support, Transaction Format V5, and new JSON API interfaces** to Polkadart. V14 and V15 continue to work as before.

The key achievements include:
- **Metadata V16**: 14 new files in `substrate_metadata` covering V16-specific features like deprecation tracking, associated types, view functions, and transaction extensions. Tested against real metadata from Polkadot, Kusama, Westend, and Paseo.
- **Transaction Format V5**: Version-aware extrinsic encoding with V5 signed (0x85), bare (0x05), and general (0x45) formats. Falls back to V4 when metadata doesn't declare V5 support. A unified extension abstraction handles both V14/V15 signed extensions and V16 transaction extensions.
- **New JSON API Interfaces**: `chainSpec_v1_*` (3 methods), `transaction_v1_*` (2 methods), and `chainHead_v1_*` (7 methods) with typed event models.

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

| Number | Deliverable |   Link    | Notes |
| -----: | ----------- | --------- | ----- |
| 0a.    | License                 | [Apache 2.0](https://github.com/justkawal/polkadart/blob/main/LICENSE) | All packages use Apache 2.0 license |
| 0b.    | Documentation           | [polkadart.dev](https://polkadart.dev) / [substrate_metadata README](https://github.com/justkawal/polkadart/tree/main/packages/substrate_metadata) / [polkadart README](https://github.com/justkawal/polkadart/tree/main/packages/polkadart) | Docs for V16 metadata, V5 transaction format, and the new JSON API interfaces |
| 0c.    | Testing                 | | ~882 tests: 102 unit tests + ~780 chain integration tests using Polkadot and Kusama V16 blocks |
| 0d.    | Docker                  | [Dockerfile](https://github.com/justkawal/polkadart/blob/main/Dockerfile) / [docker-compose.yml](https://github.com/justkawal/polkadart/blob/main/docker-compose.yml) | Run `docker compose up` to execute all tests |
| 0e.    | Article                 | | Article explaining Metadata V16, Transaction Format V5, and new JSON API features (In-Progress) |
| 1.     | Metadata V16            | [V16 implementation](https://github.com/justkawal/polkadart/tree/main/packages/substrate_metadata/lib/metadata/v16) | 14 files: RuntimeMetadataV16, ExtrinsicMetadataV16, TransactionExtensionMetadata, DeprecationInfo (3 sealed classes, 6 variants), PalletViewFunctionMetadata, PalletAssociatedTypeMetadata, StorageEntryMetadataV16. Version routing in `runtime_metadata_prefixed.dart` picks V14/V15/V16 automatically. Tested with real metadata from Polkadot, Kusama, Westend, and Paseo. |
| 2.     | Transaction Format V5   | [ExtrinsicEncoder](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/extrinsic_builder/extrinsic_encoder/extrinsic_encoder.dart) / [ExtensionBuilder](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/extrinsic_builder/extension_builder.dart) / [SigningBuilder](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/extrinsic_builder/signing_payload_builder/signing_builder.dart) / [UncheckedExtrinsicCodec](https://github.com/justkawal/polkadart/blob/main/packages/substrate_metadata/lib/derived_codecs/extrinsics/unchecked_extrinsic_codec.dart) | Detects version from metadata (V16 with `versions.contains(5)` uses V5, V14/V15 falls back to V4). Three encoding modes: signed (0x84/0x85), bare (0x04/0x05), general (0x45, V5-only). `UnifiedExtensionMetadata` handles both V14/V15 signed extensions and V16 transaction extensions. Round-trip encode/decode tests included. |
| 3.     | New JSON API Interfaces | [ChainSpecApi](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/apis/chain_spec.dart) / [TransactionApi](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/apis/transaction.dart) / [ChainHeadApi](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/apis/chain_head.dart) / [Event Models](https://github.com/justkawal/polkadart/blob/main/packages/polkadart/lib/primitives/chain_head_event.dart) | New Substrate JSON-RPC spec: `chainSpec_v1_*` (3 methods), `transaction_v1_*` (2 methods, subscription-based broadcast), `chainHead_v1_*` (7 methods, follow/unfollow session model). 11 typed event models. `ChainHeadSession` tracks active state, `TransactionBroadcast` cleans up on cancellation. 38 tests using mock provider. |

**Additional Information**

### Key Architectural Changes

**Metadata V16 (substrate_metadata):**
- `RuntimeMetadataV16`: V16 runtime metadata model with pallets, APIs, outer enums, and custom metadata
- `ExtrinsicMetadataV16`: Multi-version extrinsic support with `versions: [4, 5]` and `transactionExtensionsByVersion` mapping
- `TransactionExtensionMetadata`: Replaces V14/V15 signed extensions, uses `identifier`, `type`, and `implicit` fields

- `PalletViewFunctionMetadata`: Read-only queries with 32-byte IDs
- `PalletAssociatedTypeMetadata`: Config trait type exposure
- Extension methods give a unified API across all metadata versions
- Structures match `frame-metadata/src/v16.rs` with verified SCALE encoding order

**Transaction Format V5 (polkadart):**
- `ExtrinsicEncoder`: Reads version from metadata. If V16 metadata has `versions.contains(5)` it uses V5, otherwise V4
- Three encoding modes: signed (0x84/0x85), bare (0x04/0x05), general (0x45 for V5 only, no address/signature, just extension_version + extensions + call_data)

**New JSON API Interfaces (polkadart):**
- `ChainSpecApi`: `genesisHash()`, `chainName()`, `properties()`
- `TransactionApi`: `broadcast()` returns a `TransactionBroadcast` with operationId and event stream, `stop()` terminates the broadcast
- `ChainHeadApi` + `ChainHeadSession`: `follow()` returns a session with `header()`, `body()`, `storage()`, `call()`, `unpin()`, `unfollow()` and a typed event stream
- 11 event models covering all chain head event types (initialized, newBlock, bestBlockChanged, finalized, stop, and the operation result types)

### Test Coverage

| Suite | Tests | Status |
| ----- | ----: | ------ |
| V16 Metadata Unit | 32 | PASSED |
| V16 Chain Integration - Polkadot | ~390 | PASSED |
| V16 Chain Integration - Kusama | ~390 | PASSED |
| V5 Extrinsic Unit | 32 | PASSED |
| V5 Extrinsic Integration | 4 | PASSED |
| JSON API - ChainSpec | 4 | PASSED |
| JSON API - Transaction | 6 | PASSED |
| JSON API - ChainHead | 28 | PASSED |
| **M2 Total** | **~882** | **ALL PASSED** |

### Running Tests

Using docker-compose for the full CI pipeline:

```bash
git clone https://github.com/justkawal/polkadart
cd polkadart
docker compose up
```

Or to run all unit tests only using Docker:

```bash
git clone https://github.com/justkawal/polkadart
cd polkadart
docker build -t polkadart .
docker run --rm polkadart
```