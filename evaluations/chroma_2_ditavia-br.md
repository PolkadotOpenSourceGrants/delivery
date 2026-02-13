## Evaluation
- **Status:** Accepted
- **Application Document:** [`chroma-application.md`](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/chroma.md)
- **Milestone:** 2


| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | ------- | ---- | ---------------- |
| 1. | Talisman Wallet Context | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts` | Talisman context/config and extension path handling are implemented and unit-tested. |
| 2. | Talisman Account Import (Polkadot) | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | Polkadot mnemonic import implemented and exercised in Docker E2E (passed). |
| 3. | Talisman Authorization (Polkadot) | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | Authorization flow implemented and exercised in Docker E2E (passed). |
| 4. | Talisman Transaction Management (Polkadot) | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | Approve/reject flows implemented and exercised in Docker E2E (passed). |
| 5. | Talisman Account Import (Ethereum) | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts`, `chroma/packages/e2e-evm/tests/example.spec.ts` | Ethereum private-key import implemented and exercised in Docker E2E (passed). |
| 6. | Talisman Authorization (Ethereum) | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts`, `chroma/packages/e2e-evm/tests/example.spec.ts` | Authorization flow implemented and exercised in Docker E2E (passed). |
| 7. | Talisman Transaction Management (Ethereum) | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/talisman.ts`, `chroma/packages/e2e-evm/tests/example.spec.ts` | Approve/reject flows implemented and exercised in Docker E2E (passed). |
| 8. | Multi-chain Testing Utilities | <ul><li>[x] </li></ul> | https://chroma-docs.up.railway.app/docs/guides/multi-chain, `chroma/packages/e2e-evm/tests/helpers/multi-chain.ts`, `chroma/packages/e2e-evm/tests/talisman.spec.ts` | App-level helper utilities and a chain-switch test (approve + reject) are now present and documented. The docs explicitly justify app-level helpers instead of library utilities, which satisfies the milestone scope. |
| 9. | Documentation/Landing Page Website | <ul><li>[x] </li></ul> | https://chroma-docs.up.railway.app/docs | Documentation site is live and accessible. |

**Additional notes**
- Docker E2E runs succeeded for both `E2E_TARGET=polkadot-js` and `E2E_TARGET=evm` (1 test each).
- Wallet interaction functions in `talisman.ts` are excluded from unit coverage (`c8 ignore`) and rely on E2E validation only.
- The multi-chain guide documents rejection/approval flows, and the repo now includes a helper plus a test that covers both paths.
- E2E coverage is currently limited to single happy‑path tests; expanding error/edge-case coverage (including chain switching) would strengthen confidence.

**Requested follow-ups**
1. Expand E2E coverage beyond single happy‑path tests (additional chains, error cases, retries).
