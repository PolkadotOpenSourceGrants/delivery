## Evaluation
- **Status:** Changes Requested
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
| 8. | Multi-chain Testing Utilities | <ul><li>[ ] </li></ul> | `chroma/packages/e2e-evm/src/components/Connect.vue` | App-level chain selector UI and `switchChainAsync` were added, but the application requires library-level utilities or documented helpers for multi-chain testing. The current update does not introduce library utilities or a documented test recipe, so the deliverable remains incomplete. |
| 9. | Documentation/Landing Page Website | <ul><li>[x] </li></ul> | https://chroma-docs.up.railway.app/docs | Documentation site is live and accessible. |

**Additional notes**
- Docker E2E runs succeeded for both `E2E_TARGET=polkadot-js` and `E2E_TARGET=evm` (1 test each).
- Wallet interaction functions in `talisman.ts` are excluded from unit coverage (`c8 ignore`) and rely on E2E validation only.
- E2E coverage is currently limited to single happy‑path tests; expanding error/edge-case coverage (including chain switching) would strengthen confidence.

**Requested follow-ups**
1. Provide library-level multi-chain testing utilities (e.g., helper that wraps chain switching + wallet confirmation), or explicitly document and publish a supported recipe in the Chroma docs and test matrix that demonstrates how to do multi-chain testing with the existing API.
2. Add E2E tests that validate chain switching (e.g., switch from Paseo Asset Hub to Moonbase Alpha and confirm wallet approval flow), including a failure case or rejected switch.


