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
| 8. | Multi-chain Testing Utilities | <ul><li>[ ] </li></ul> | https://chroma-docs.up.railway.app/docs/guides/multi-chain, `chroma/packages/e2e-evm/src/components/Connect.vue`, `chroma/packages/e2e-evm/tests/example.spec.ts` | A multi-chain guide now exists and the EVM app includes a chain selector UI, but there are still no library-level utilities and the E2E test does not include a chain-switch rejection case. This falls short of the multi-chain utilities deliverable as specified. |
| 9. | Documentation/Landing Page Website | <ul><li>[x] </li></ul> | https://chroma-docs.up.railway.app/docs | Documentation site is live and accessible. |

**Additional notes**
- Docker E2E runs succeeded for both `E2E_TARGET=polkadot-js` and `E2E_TARGET=evm` (1 test each).
- Wallet interaction functions in `talisman.ts` are excluded from unit coverage (`c8 ignore`) and rely on E2E validation only.
- The multi-chain guide documents rejection/approval flows, but the current `e2e-evm` test only approves the chain switch; no rejection path is asserted in code.
- E2E coverage is currently limited to single happy‑path tests; expanding error/edge-case coverage (including chain switching) would strengthen confidence.

**Requested follow-ups**
1. Provide library-level multi-chain testing utilities (e.g., helper that wraps chain switching + wallet confirmation), or explicitly document why app-level guides are sufficient for the deliverable.
2. Update the E2E test to cover the chain-switch rejection case shown in the docs.
