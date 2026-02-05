# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [chroma](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/chroma.md)
* **Milestone Number:** 1
* **DOT Payment Address:** `162RtNYMpw3beFFpJqvjXp2GLUEf7EkwL3aRGEKkggVKc3Gq`

**Context**

Chroma is an end-to-end (E2E) testing library for Polkadot wallet interactions built on top of Playwright. It provides ready-to-use test fixtures and utilities to simplify testing of dApps that interact with browser wallet extensions. The library currently supports Polkadot.js Extension and Talisman wallets, enabling developers to write automated tests for account imports (mnemonic/private key), dApp authorization, and transaction signing workflows.

**Deliverables**

| Number | Deliverable | Link |
| -----: | ----------- | ------------- |
| 0a. | License | https://github.com/avalix-labs/chroma/blob/main/LICENSE |
| 0b. | Documentation | https://github.com/avalix-labs/chroma/blob/main/packages/chroma/README.md |
| 0c. | Testing and Testing Guide | https://github.com/avalix-labs/chroma/blob/main/README.md#running-tests-with-docker |
| 0d. | Docker | https://github.com/avalix-labs/chroma/blob/main/Dockerfile |
| 0e. | Article | - https://forum.polkadot.network/t/introducing-e2e-testing-library-for-polkadot-dapps/15025 <br> - https://x.com/0xPresc/status/1970166415736098900 |
| 1. | NPM Package Setup | https://github.com/avalix-labs/chroma/blob/main/.github/workflows/release.yml |
| 2. | Polkadot.js Extension Context | https://github.com/avalix-labs/chroma/blob/main/packages/chroma/src/wallets/polkadot-js.ts |
| 3. | Account Import Fixtures | https://github.com/avalix-labs/chroma/blob/2c9cd3146705ecc53bea638b67d73bd7093fa93e/packages/chroma/src/wallets/polkadot-js.ts#L57 |
| 4. | Authorization Fixtures | https://github.com/avalix-labs/chroma/blob/2c9cd3146705ecc53bea638b67d73bd7093fa93e/packages/chroma/src/wallets/polkadot-js.ts#L98 |
| 5. | Transaction Management Fixtures | - https://github.com/avalix-labs/chroma/blob/2c9cd3146705ecc53bea638b67d73bd7093fa93e/packages/chroma/src/wallets/polkadot-js.ts#L122 <br> - https://github.com/avalix-labs/chroma/blob/2c9cd3146705ecc53bea638b67d73bd7093fa93e/packages/chroma/src/wallets/polkadot-js.ts#L136 |

**Additional Information**

Chroma supports the latest Playwright version (^1.55.0), which is important as [Playwright v1.55.0](https://github.com/microsoft/playwright/releases/tag/v1.55.0) dropped support for Chromium extension manifest v2. The wallet extensions bundled with Chroma (Polkadot.js Extension v0.61.7 and Talisman v3.0.5) use manifest v3, ensuring compatibility with current and future Playwright releases.
