# Evaluation

Status: In Progress

Application Document: https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/chroma.md

Milestone: 1

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | ------- | ---- | ---------------- |
| 0a. | License | <ul><li>[x] </li></ul> | chroma/LICENSE | MIT license present in the repository root. |
| 0b. | Documentation | <ul><li>[ ] </li></ul> | chroma/README.md, chroma/packages/chroma/README.md | Docs exist and cover setup/usage. However, extension versions listed do not match the versions pinned in code. Also, docs do not include a clear, reproducible test matrix (which tests validate which features). |
| 0c. | Testing and Testing Guide | <ul><li>[ ] </li></ul> | chroma/README.md, chroma/packages/chroma/tests/ | Playwright E2E specs exist but are the only tests. There is no unit test suite or coverage tooling. Test execution in Docker resulted in 6 passing, 1 failing, 1 skipped, and 1 flaky test (failure in tests/dapp/turtle-cool.spec.ts due to external site load/timeout). This does not meet the application claim of comprehensive unit + integration coverage. |
| 0d. | Docker | <ul><li>[ ] </li></ul> | chroma/Dockerfile | Docker build and run succeeded, but the Playwright suite reported a failing test and a flaky test (external dependency). Docker success is not sufficient without a green test run. |
| 0e. | Article | <ul><li>[ ] </li></ul> | Links in chroma-m1-delivery.md | Forum post was reviewed and is an announcement/overview (features, previews, links) but does not provide a tutorial-style walkthrough or implementation guide as promised. The X link appears to be a video demo rather than an article, and it could not be accessed without login, so its content could not be verified. |
| 1. | NPM Package Setup | <ul><li>[x] </li></ul> | chroma/.github/workflows/release.yml | Changesets-based release workflow in place. |
| 2. | Polkadot.js Extension Context | <ul><li>[ ] </li></ul> | chroma/packages/chroma/src/context-playwright/index.ts, chroma/packages/chroma/src/wallets/polkadot-js.ts | Implementation exists and some E2E flows passed, but overall suite did not pass, so verification is incomplete. |
| 3. | Account Import Fixtures | <ul><li>[ ] </li></ul> | chroma/packages/chroma/src/wallets/polkadot-js.ts, chroma/packages/chroma/tests/polkadot-js.spec.ts | Fixture exists and is exercised by E2E tests; relevant tests passed in Docker, but overall suite is not green. |
| 4. | Authorization Fixtures | <ul><li>[ ] </li></ul> | chroma/packages/chroma/src/wallets/polkadot-js.ts, chroma/packages/chroma/tests/polkadot-js.spec.ts | Fixture exists and is exercised by E2E tests; relevant tests passed in Docker, but overall suite is not green. |
| 5. | Transaction Management Fixtures | <ul><li>[ ] </li></ul> | chroma/packages/chroma/src/wallets/polkadot-js.ts, chroma/packages/chroma/tests/polkadot-js.spec.ts | Approve/reject fixtures exist and are referenced in E2E tests; relevant tests passed in Docker, but overall suite is not green. |

## Additional notes

The docs list Polkadot JS v0.61.7 and Talisman v3.0.5, but the code pins Polkadot JS v0.62.6 and Talisman v3.1.13. The documentation should be updated to match the actual versions used by the download script.

Test coverage tooling (e.g., c8/nyc/istanbul/vitest/jest) is not configured, so coverage cannot be measured. The existing tests are E2E-only and depend on external dApps and extension UIs.

Docker run results: 6 passed, 1 failed, 1 skipped, 1 flaky. Failure was in tests/dapp/turtle-cool.spec.ts due to a page timeout on https://app.turtle.cool/ (external dependency).

Several tests use live URLs (Vercel or Polkadot JS Apps). This creates flakiness and makes CI reproducibility unclear without pinned test environments.

Forum post content reviewed: introductory overview, feature list, and demo links; no step-by-step tutorial or implementation guide.

X link appears to be a video demo what is not actually an article.

The Talisman E2E test under packages/chroma/tests/talisman-wallet.spec.ts is marked test.skip, and a TODO indicates it is deferred to milestone 2.


## Requested follow-ups

Align packages/chroma/README.md wallet/extension versions with the versions pinned in code.

Provide a reproducible test matrix mapping each deliverable to specific tests and expected outputs.

Add unit/integration tests with coverage instrumentation, or justify why E2E-only tests are sufficient for Milestone 1.

Provide instructions to run tests in headed mode (visible browser + extensions) and a screen recording of a full green run.
E2E scope check

The current E2E suite is not sufficient to fully cover the Milestone 1 scope as defined in the application. It validates some Polkadot.js flows against external dApps, but lacks comprehensive coverage of edge cases, error handling, and unit-level validation for fixtures; it also includes external dependencies and a skipped wallet test.
