# Evaluation

- **Status:** Accepted 
- **Application Document:** [Polkadot Java SDK](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadot-java-sdk.md)
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | -------- | ---- | ---------------- |
| 0a. | License | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/blob/main/LICENSE | Apache 2.0 license present at repository root. |
| 0b. | Documentation | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/blob/main/README.md<br>https://methodfive.github.io/jot/quickstart/ | Hosted docs, Quick Start, and Javadoc cover setup; now explicitly note JDK 21+ support and Rust toolchain requirement. Examples section calls out prerequisites (funded account vs. local dev node / smoldot). |
| 0c. | Usage Examples | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/tree/main/jot-examples | Examples README documents configuration, funded mnemonic, and Maven entry points (`RunAllReadOnly`, `RunAll`) that work cross-platform. Verified both commands succeed against Westend with provided config. |
| 1. | SDK Core | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/tree/main/jot | `mvn -pl jot -am verify` passes on JDK 21/25; JaCoCo integrated, coverage now 90% instructions / 77% branches with new tests for entity/query/rpc/events and metadata cache. Maven warnings removed (pinned `maven-javadoc-plugin`). |
| 2. | SDK Extensions | <ul><li>[x] </li></ul> | https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot | SLF4J binding added, Ant rename step guarded, higher-level typed API exposed via `api.query()/api.tx()/api.subscribe()` aligning with Papi ergonomics. |
| 3. | Documentation & Examples Comparison | <ul><li>[x] </li></ul> | https://github.com/polkadot-api/polkadot-api | Docs now mirror Papi’s clarity: root README lists environment setup (`source ~/.cargo/env`, JDK 21), `jot-examples/README.md` covers offline signing, events, query iteration, and Maven commands. |

## Testing & Coverage Summary

- `mvn -pl jot -am verify`: ✅ (JDK 21 and JDK 25). Coverage: 90% instructions / 77% branches from JaCoCo aggregate report.
- Examples: `mvn -pl jot-examples exec:java -Dexec.mainClass="com.method5.jot.util.RunAllReadOnly"` (read-only) and `RunAll` (transactional) both succeed using documented Westend-funded mnemonic.

## Recommendations (inspired by polkadot-api “papi”)

Resolved recommendations: examples runnable cross-platform, documentation updated, typed API facade introduced, build warnings removed, coverage expanded with new tests (offline signing, events, query iteration).

## General Notes

- Clean build (no SLF4J/Ant warnings). Examples/documentation now aligned with Papi-inspired best practices.
- Sr25519 remains JNI-backed; pure-Java/WASM crypto could be added later (optional risk-managed module) if Android/mobile support becomes a priority.



