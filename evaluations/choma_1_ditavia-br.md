## Evaluation
- **Status:** Accepted
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/chroma.md
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | ------- | ---- | ---------------- |
| 0a. | License | <ul><li>[x] </li></ul> | `chroma/LICENSE` | MIT license present in the repository root. |
| 0b. | Documentation | <ul><li>[x] </li></ul> | `chroma/README.md`, `chroma/packages/chroma/README.md`, `chroma/packages/chroma/TEST_MATRIX.md` | Docs cover setup/usage, include a test matrix, and reference external docs; combined with the Medium tutorial, this meets the documentation scope. |
| 0c. | Testing and Testing Guide | <ul><li>[x] </li></ul> | `chroma/README.md`, `chroma/packages/chroma/src/**/*.test.ts`, `chroma/packages/chroma/vitest.config.ts`, `chroma/packages/e2e-*` | Unit/integration tests now cover core fixtures with high coverage (see notes). E2E suites passed in Docker for `e2e-polkadot-js` and `e2e-evm`, and locally for `e2e-polkadot-js`. While E2E breadth remains limited, the core unit/integration coverage meets the milestone requirement. |
| 0d. | Docker | <ul><li>[x] </li></ul> | `chroma/Dockerfile` | Docker image built and both `E2E_TARGET=polkadot-js` and `E2E_TARGET=evm` test runs passed. |
| 0e. | Article | <ul><li>[x] </li></ul> | https://medium.com/@avalix/end-to-end-wallet-testing-for-smart-contracts-on-polkadot-using-playwright-and-chroma-d7ef1b18b81b | Medium article provides a tutorial-style walkthrough and setup narrative aligned with the application’s requirement. |
| 1. | NPM Package Setup | <ul><li>[x] </li></ul> | `chroma/.github/workflows/release.yml` | Changesets-based release workflow in place. |
| 2. | Polkadot.js Extension Context | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/context-playwright/index.ts`, `chroma/packages/chroma/src/context-playwright/index.test.ts` | Unit tests cover the context fixture setup and wallet wiring; E2E smoke tests also pass. |
| 3. | Account Import Fixtures | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/chroma/src/wallets/polkadot-js.test.ts` | Unit tests cover import flows; E2E smoke test also exercises import. |
| 4. | Authorization Fixtures | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/chroma/src/wallets/polkadot-js.test.ts` | Unit tests cover authorize flows; E2E smoke test also exercises authorization. |
| 5. | Transaction Management Fixtures | <ul><li>[x] </li></ul> | `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/chroma/src/wallets/polkadot-js.test.ts` | Unit tests cover approve/reject flows; E2E smoke test exercises both approve and reject. |

**Additional notes**
- Unit/integration coverage (Vitest v8): `All files` 98.46% statements / 94.44% branches / 70% functions / 98.43% lines. `src/context-playwright` and `src/wallets` are 100%; `src/utils/download-extension.ts` is ~97.5% lines. `src/index.ts` shows 0% because it is a re-export entry.
- Local E2E run for `e2e-polkadot-js` passed after running Playwright locally; Dockerized E2E runs for `polkadot-js` and `evm` also passed.
