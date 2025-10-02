# Evaluation

- **Status:** In progress
- **Application Document:** [Polkadot Java SDK](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadot-java-sdk.md)
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | -------- | ---- | ---------------- |
| 0a. | License | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/blob/main/LICENSE | Apache 2.0 license present at repository root. |
| 0b. | Documentation | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/blob/main/README.md<br>https://methodfive.github.io/jot/quickstart/ | Hosted docs, Quick Start, and Javadoc exist; recommend clarifying supported JDK versions (tests pass on JDK 21 after installing Rust toolchain, Mockito fails on JDK 25) and expanding the example section with explicit prerequisites (funded account vs. local dev node / smoldot). |
| 0c. | Usage Examples | <ul><li>[ ] </li></ul> | https://github.com/methodfive/jot/tree/main/jot-examples | 40+ examples compile, but transactional demos fail out of the box (`code 1010: Inability to pay fees`). Please supply a Maven-based profile or other cross-platform command that exercises the examples and document how to configure a funded account or local dev chain so submissions succeed. |
| 1. | SDK Core | <ul><li>[ ] </li></ul> | https://github.com/methodfive/jot/tree/main/jot | Unit suite (`mvn -pl jot -am test`) passes on JDK 21 with Rust tooling. Jacoco report shows 68% instruction / 61% branch coverage; increase coverage for low-tested areas (`com.method5.jot.entity`, `query`, `events`, `rpc`) and add the JaCoCo plugin to the build so reports are reproducible. Maven also warns about the missing `maven-javadoc-plugin` version—pinning it will future-proof the build. |
| 2. | SDK Extensions | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot | Wallet, signing (sr25519/ed25519), multisig, SCALE codec, and RPC abstractions are implemented. Clean recurring build noise (SLF4J binding, Ant rename step complaining about absent `.so/.dll` artefacts on macOS) and consider adding higher-level typed helpers similar to Papi’s descriptor-based API. |
| 3. | Documentation & Examples Comparison | <ul><li>[ ] </li></ul> | https://github.com/polkadot-api/polkadot-api | Compared to Papi’s runnable Bun/Vite examples and light-client defaults, Jot lacks easy-to-run scenarios. We recommend (a) publishing a doc or README in `jot-examples` explaining how to run the examples, (b) providing a profile that runs examples against a local dev node or light client, (c) expanding examples to cover offline signing, events decoding, and query-model iteration. |

## Testing & Coverage Summary

- `mvn -pl jot -am test`: ✅ on JDK 21 (requires sourcing `~/.cargo/env`). Mockito/Byte Buddy rejects JDK 25 classfile version 69; either document the JDK requirement or upgrade dependencies. 
- `mvn -pl jot -am org.jacoco:jacoco-maven-plugin:0.8.12:prepare-agent test ...`: ✅ generates coverage (68% instruction / 61% branch). Adding the JaCoCo plugin to the POM would make coverage reproducible without CLI overrides.
- Example sweep (`run-all-examples.sh`): read-only demos succeed (wallet generation, metadata parsing, SCALE encoding, RPC/subscriptions); every extrinsic-submitting example fails with `code 1010` due to unfunded accounts. 

## Recommendations (inspired by polkadot-api “papi”)

1. **Example UX**: Ship a dev-node profile or smoldot integration so transactional examples succeed by default, similar to Papi’s Bun examples that target Westend dev accounts.
2. **Documentation polish**: Add an examples README covering prerequisites, one-line Maven commands, and how to override endpoints/keys. Note the JDK requirement and Rust toolchain step in Getting Started.
3. **Higher-level typed API**: Consider generating metadata-driven builders or fluent wrappers to match Papi’s typed descriptors, reducing manual SCALE handling in Java.
4. **CI/build hygiene**: Pin `maven-javadoc-plugin` version, include a test-scope SLF4J binding, guard the Ant rename step, and add optional integration tests for read-only examples. 
5. **Expanded examples/tests**: Add offline signing, events decoding, query-model iteration, and error-handling demos. Increase automated coverage for low-covered modules.

## General Notes

- Build warnings are consistent across runs: missing plugin version, SLF4J NOP logger, Ant warnings about absent `.so/.dll`. Addressing them will tighten CI parity with other ecosystem SDKs.
- Overall deliverables align with the proposal, but improving example usability and documentation will help the SDK match the developer experience of widely adopted tooling such as Papi.

## Reference examples in polkadot-api for inspiration:
  - Offline signing: polkadot-api/examples/bun/src/offline.ts
  - Event decoding: polkadot-api/examples/bun/src/multisig.ts, polkadot-api/examples/ink/index.ts, polkadot-api/examples/vite/src/main.ts
  - Query/model iteration: polkadot-api/examples/bun/src/ledger.ts, polkadot-api/examples/bun/src/rpc.ts, polkadot-api/examples/bun/src/switch-rpcs.ts, polkadot-api/examples/react-teleport/src/TransferrableBalance.tsx


