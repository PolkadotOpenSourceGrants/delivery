# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Polkadot Java SDK](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/polkadot-java-sdk.md)
* **Milestone Number:** All milestones.
* **DOT Payment Address:** `14zb7FpKGRCoW8SPezDHsMzqhGAuEn6Wjprf4j2Gn85dGVEh`

**Context**

This submission completes all milestones for the Polkadot Java SDK (named Jot).
The project delivers a modern, actively maintained Java SDK for Polkadot/Substrate networks, with a custom SCALE codec, runtime metadata parser, RPC abstraction layer, key management, transaction signing, and extrinsic submission.

Alongside the core SDK, we provide full documentation, Javadoc, and usage examples to ensure developers can easily integrate with Substrate-based chains from any JVM environment. This fills a longstanding tooling gap for Java in the Polkadot ecosystem.

Repository: https://github.com/methodfive/jot

Docs: https://methodfive.github.io/jot

**Deliverables**

| Number | Deliverable | Link                                                                                                                                                                                                                                                                                     | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------ | ----------- |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0a. | License (Apache 2.0) | [License](https://github.com/methodfive/jot/blob/main/LICENSE)                                                                                                                                                                                                                           | Apache 2.0 license committed at project root.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| 0b. | Documentation | [Docs Homepage](https://methodfive.github.io/jot/) <br><br> [Project Readme](https://github.com/methodfive/jot/blob/main/README.md) <br><br> [Quick Start Guide](https://methodfive.github.io/jot/quickstart/) <br><br> [Javadoc](https://methodfive.github.io/jot/api/index.html) | • Project Readme provides project overview and installation instructions.<br>• Quick Start guide covers project setup and basic connectivity.<br>• Javadoc generated for all major classes and interfaces.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 0c. | Usage Examples | [Examples](https://github.com/methodfive/jot/tree/main/jot-examples/src/main/java/com/method5/jot/examples)                                                                                                                                                                              | 50+ runnable usage examples covering balances, staking, multisig, governance, subscriptions, etc. (See details below)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 1. | SDK Core | [Jot Repository](https://github.com/methodfive/jot)                                                                                                                                                                                                                                      | Includes:<br>• SCALE codec ([scale](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/scale))<br>• Runtime metadata parser ([metadata](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/metadata))<br>• RPC interface abstraction ([rpc & wss](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/rpc)) with base methods (`chain_getBlock`, `state_getStorage`, etc.)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 2. | SDK Extensions | [Jot Repository](https://github.com/methodfive/jot)                                                                                                                                                                                                                                      | Adds:<br>• Key management and transaction signing ([wallet](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/wallet), [signing](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/crypto))<br>• Extrinsic construction and submission (`author_submitExtrinsic`, etc.) ([extrinsic](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/extrinsic))<br>• Error decoding ([event parser](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/events))<br>• Support for common extrinsics (Balances, ConvictionVoting, Multisig, Staking, System, Utility) and queries (Author, Chain, Payment, State, Storage, System). ([query](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/query)) ([call](https://github.com/methodfive/jot/tree/main/jot/src/main/java/com/method5/jot/extrinsic/call)) |


**Usage Examples Included**

- Balance transfers (transfer all, transfer allow death, transfer keep alive). 
- Open gov voting (voting and removing vote). 
- Multisig support (approvals). 
- Parsing extrinsics. 
- Receiving results of submitted extrinsic. 
- Staking, Bonding more, chilling, nomination, rebounding, unbending, and paying out stakers, etc.
- System remarks. 
- Several batch extrinsic examples. 
- Working with ED25519 Wallets. 
- Working with SR25519 Wallets. 
- Parsing Metadata. 
- Querying account balances. 
- Querying asset balances. 
- Querying blocks, block events, etc.
- Querying fee info. 
- Querying finalized and best states. 
- Querying nonce. 
- Querying runtime info & version. 
- Connecting to RPC and WS nodes. 
- Scale encoding & decoding. 
- SS58 Address Conversion. 
- Various subscription examples (Receiving new blocks, etc)
- And more..

**Additional Information**

- All deliverables have been tested against both local Substrate nodes and public Polkadot endpoints.
- Artifacts are published to **Maven Central** under `com.method5:jot`, ensuring simple dependency management for Java developers.
- We are committed to long-term maintenance, issue triage, and community support under Method5.  