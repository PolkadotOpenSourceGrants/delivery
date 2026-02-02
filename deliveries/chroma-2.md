# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [chroma](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/chroma.md)
* **Milestone Number:** 2
* **DOT Payment Address:** `162RtNYMpw3beFFpJqvjXp2GLUEf7EkwL3aRGEKkggVKc3Gq`

**Context**

Milestone 2 extends Chroma with multi-wallets support. This milestone adds comprehensive testing capabilities through Talisman wallet integration, including account management, authorization flows, and transaction handling. Additionally, this milestone includes a dedicated documentation website and landing page for Chroma.

**Deliverables**

| Number | Deliverable | Link |
| -----: | ----------- | ------------- |
| 1. | Talisman Wallet Context | https://github.com/avalix-labs/chroma/blob/c18a42dc1fca7413272ef2518fa16dfdecc6b9fa/packages/chroma/src/wallets/talisman.ts#L7-L13 |
| 2. | Talisman Account Import (Polkadot) | https://github.com/avalix-labs/chroma/blob/c18a42dc1fca7413272ef2518fa16dfdecc6b9fa/packages/chroma/src/wallets/talisman.ts#L117-L146 |
| 3. | Talisman Authorization (Polkadot) | https://github.com/avalix-labs/chroma/blob/c18a42dc1fca7413272ef2518fa16dfdecc6b9fa/packages/chroma/src/wallets/talisman.ts#L182-L206 |
| 4. | Talisman Transaction Management (Polkadot) | https://github.com/avalix-labs/chroma/blob/c18a42dc1fca7413272ef2518fa16dfdecc6b9fa/packages/chroma/src/wallets/talisman.ts#L208-L237 |
| 5. | Talisman Account Import (Ethereum) | https://github.com/avalix-labs/chroma/blob/c18a42dc1fca7413272ef2518fa16dfdecc6b9fa/packages/chroma/src/wallets/talisman.ts#L148-L179 |
| 6. | Talisman Authorization (Ethereum) | Same with no.3 |
| 7. | Talisman Transaction Management (Ethereum) | Same with no.4 |
| 8. | Multi-chain Testing Utilities | Multi-wallet covered in this file: https://github.com/avalix-labs/chroma/blob/c18a42dc1fca7413272ef2518fa16dfdecc6b9fa/packages/e2e-polkadot-js/tests/polkadot.spec.ts. including all api interface between polkadot-js and talisman |
| 9. | Documentation/Landing Page Website | https://chroma-docs.up.railway.app/docs |

**Additional Information**

What sets Chroma apart from existing E2E wallet testing solutions:

- **Full TypeScript Support**: Chroma is built with TypeScript, providing type safety, better IDE autocompletion, and improved developer experience
- **Official VSCode Playwright Extension Support**: Seamless integration with the official Playwright Test for VSCode extension, enabling features like test debugging, test generation, and visual test runner directly in the IDE
- **Chromium Extension Manifest v3 Compatibility**: Chroma supports the latest Playwright version (^1.55.0) which dropped support for Chromium extension manifest v2. The wallet extensions bundled with Chroma (Polkadot.js Extension and Talisman) use manifest v3, ensuring compatibility with current and future Playwright releases

**E2E Testing Coverage**

All API interfaces between Polkadot.js Extension and Talisman are covered with E2E testing, including:
- Polkadot.js Extension → Substrate account
- Talisman → Substrate account
- Talisman → Ethereum account

You can verify the tests by running the following Docker commands:

```bash
# Build the Docker image
docker build -t chroma-test .

# Run e2e-polkadot-js tests
docker run --rm --shm-size=2gb -e E2E_TARGET=polkadot-js chroma-test

# Run e2e-evm tests
docker run --rm --shm-size=2gb -e E2E_TARGET=evm chroma-test
```
