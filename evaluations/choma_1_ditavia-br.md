## Evaluation
- **Status:** In Progress
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/chroma.md
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | ------- | ---- | ---------------- |
| 0a. | License | <ul><li>[x] </li></ul> | `chroma/LICENSE` | MIT license present in the repository root. |
| 0b. | Documentation | <ul><li>[ ] </li></ul> | `chroma/README.md`, `chroma/packages/chroma/README.md` | Docs exist and cover setup/usage. Extension versions now match code, but the documentation still lacks a clear test matrix mapping deliverables to tests and does not include a tutorial-style walkthrough as described in the application. |
| 0c. | Testing and Testing Guide | <ul><li>[ ] </li></ul> | `chroma/README.md`, `chroma/packages/chroma/tests/`, `chroma/packages/chroma/src/utils/*test.ts`, `chroma/packages/e2e-*` | Unit and integration tests were added for extension download logic and run locally (10 tests passed). E2E suites passed both in Docker and locally for `e2e-polkadot-js` (1 test), and in Docker for `e2e-evm` (1 test). Coverage is still limited to the download-extension module and E2E coverage remains narrow (single happy‑path tests), so this still falls short of “core functions fully covered” across fixtures and flows. |
| 0d. | Docker | <ul><li>[x] </li></ul> | `chroma/Dockerfile` | Docker image built and both `E2E_TARGET=polkadot-js` and `E2E_TARGET=evm` test runs passed. |
| 0e. | Article | <ul><li>[x] </li></ul> | https://medium.com/@avalix/end-to-end-wallet-testing-for-smart-contracts-on-polkadot-using-playwright-and-chroma-d7ef1b18b81b | Medium article provides a tutorial-style walkthrough and setup narrative aligned with the application’s requirement. |
| 1. | NPM Package Setup | <ul><li>[x] </li></ul> | `chroma/.github/workflows/release.yml` | Changesets-based release workflow in place. |
| 2. | Polkadot.js Extension Context | <ul><li>[ ] </li></ul> | `chroma/packages/chroma/src/context-playwright/index.ts`, `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | E2E run passed in Docker and locally, but only a single happy‑path test validates it; broader coverage is still missing. |
| 3. | Account Import Fixtures | <ul><li>[ ] </li></ul> | `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | Fixture is exercised in Docker and local E2E (happy path) but lacks unit‑level coverage and edge‑case tests. |
| 4. | Authorization Fixtures | <ul><li>[ ] </li></ul> | `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | Fixture is exercised in Docker and local E2E (happy path) but lacks unit‑level coverage and edge‑case tests. |
| 5. | Transaction Management Fixtures | <ul><li>[ ] </li></ul> | `chroma/packages/chroma/src/wallets/polkadot-js.ts`, `chroma/packages/e2e-polkadot-js/tests/polkadot.spec.ts` | Approve/reject flows are exercised in Docker and local E2E (happy path) but lack broader coverage. |

**Additional notes**
- Unit and integration tests for `download-extension` were added and passed locally (10 tests total). Coverage is now available via Vitest for that module only.
- Local E2E run for `e2e-polkadot-js` passed after running Playwright locally; Dockerized E2E runs for `polkadot-js` and `evm` also passed.
- Several tests use live URLs (Vercel or Polkadot JS Apps). This creates flakiness and makes CI reproducibility unclear without pinned test environments.
- No documentation or delivery note explains how to generate coverage (e.g., `vitest --coverage`), so coverage is not reproducible from the provided instructions.
- Coverage report (Vitest v8) shows low overall coverage: `All files` 14.08% statements / 15.09% branches / 6.81% functions / 14.13% lines, with non-test modules in `src/context-playwright` and `src/wallets` at 0%. The only well-covered area is `src/utils/download-extension.ts` (~97.5% lines).
- Forum post content reviewed: introductory overview, feature list, and demo links; still useful but not a tutorial.
- X link appears to be a video demo, not an article.
- The Talisman E2E test under `packages/chroma/tests/talisman-wallet.spec.ts` is marked `test.skip`, and a `TODO` indicates it is deferred to milestone 2.

**Requested follow-ups**
1. Provide a reproducible test matrix mapping each deliverable to specific tests and expected outputs.
2. Add unit/integration tests with coverage instrumentation for wallet fixtures, or justify why E2E-only tests are sufficient for Milestone 1.
3. Document how to generate coverage reports (commands and expected outputs).
4. Provide instructions to run tests in headed mode (visible browser + extensions), including Playwright browser install steps, and a screen recording of a full green run.

**E2E scope check**
- The new `e2e-polkadot-js` and `e2e-evm` suites passed in Docker, but they are single happy‑path tests and do not fully cover Milestone 1 scope (error handling, edge cases, fixture‑level validations).
