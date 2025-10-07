# Evaluation

- **Status:** Accepted
- **Application Document:** [create-dot-app](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/create-dot-app.md)
- **Milestone Number:** 1


**Deliverables**

| Number | Deliverable | Accepted | Link | Notes |
| ------ | ----------- | -------- | ---- |-------|
| 0a. | License | <ul><li>[x]</li></ul> | https://github.com/preschian/create-dot-app/blob/main/LICENSE | - | 
| 0b. | Documentation | <ul><li>[x]</li></ul> | https://github.com/preschian/create-dot-app/blob/main/README.md | - | 
| 0c. | Testing | <ul><li>[x]</li></ul> | integration test for templates: https://github.com/preschian/create-dot-app/blob/main/.github/workflows/package-manager.yml<br>integration test for cli: https://github.com/preschian/create-dot-app/blob/main/cli/TESTING.md |  |
| 0d. | Repository | <ul><li>[x]</li></ul> | https://github.com/preschian/create-dot-app | - |
| 0e. | Article | <ul><li>[x]</li></ul> | https://forum.polkadot.network/t/create-dot-app-the-scaffolding-tool-for-all-your-polkadot-dapp-ideas/14297/1 | - |
| 1. | CLI Core Framework | <ul><li>[x]</li></ul> | https://github.com/preschian/create-dot-app/blob/027de303e5ed357b545c9cf28b0d7d3766ca35fa/cli/src/index.ts#L64-L72 | - |
| 2. | Template Engine | <ul><li>[x]</li></ul> | https://github.com/preschian/create-dot-app/blob/main/cli/src/template-selector.ts | - |
| 3. | React Templates | <ul><li>[x]</li></ul> | react-dedot: https://github.com/preschian/create-dot-app/tree/main/templates/react-dedot<br>react-papi: https://github.com/preschian/create-dot-app/tree/main/templates/react-papi |  |
| 4. | Vue Templates | <ul><li>[x]</li></ul> | vue-dedot: https://github.com/preschian/create-dot-app/tree/main/templates/vue-dedot<br>vue-papi: https://github.com/preschian/create-dot-app/tree/main/templates/vue-papi |  |
| 5. | NPM Package Distribution | <ul><li>[x]</li></ul> | https://github.com/preschian/create-dot-app/blob/main/.github/workflows/release.yml<br>https://www.npmjs.com/package/create-dot-app?activeTab=readme |  |





Here are some suggestions for improvements to the project. They’re not mandatory, but they could help enhance your project even further.


## 1. Subscription & Memory-Leak Hygiene

**Problem**: Block listeners and transaction watchers are created but never disposed, so they accumulate on hot-reloads / navigation.

**Fix**
- Return the *unsubscribe* handle from every helper (`subscribeToBlocks`, `signSubmitAndWatch`, `api.query.system.events`).
- In UI layers (`useEffect` / `onMounted`), store the handle and call it in the cleanup phase (`return () => unsub()` / `onUnmounted`).

**Why it matters**: Prevents growing WebSocket traffic and stale callbacks that can race or crash the app after a few reloads.

---

## 2. Hash Label vs. Data Mismatch

**Problem**: UI labels the value as **“Transaction Hash”** but actually holds a **block hash** (`BestChainBlockIncluded.blockHash`) and links to `/block/{hash}` on Subscan.

**Fix (pick one)**
1. **Rename label** to **“Block Hash”** (and keep the existing link), **or**
2. If you need the *extrinsic* hash:
   - Capture it from the tx events (`result.txHash` or `event.extrinsicHash`).
   - Link to `/extrinsic/{hash}`.

**Why it matters**: Keeps UX truthful and avoids confusion when users look up the hash on explorers.

---

## 3. Balance Precision

**Problem**: `formatPrice` converts on-chain `u128` balances with `Number(...)`.  Large DOT values exceed JS’ safe integer range and lose precision.

**Fix**
- Use `BigInt` or a decimal helper (`@polkadot/util` → `formatBalance`, or `big.js`).
- Format human-readable output with `Intl.NumberFormat` after converting to decimal string.

**Why it matters**: Prevents silent rounding errors and guarantees accurate balance display.

---

## 4. Transaction Watcher Lifecycle

**Problem**: `signSubmitAndWatch` / `signAndSend` return a subscription object but it’s never unsubscribed once the tx is finalized or fails.

**Fix**
- Capture the subscription and call `.unsubscribe()` in the success & error branches.

**Why it matters**: Releases RPC bandwidth and avoids duplicate event handling when a user sends multiple transactions.

---

## 5. Wallet `enable()` Identifier

**Problem**: Hard-coded dapp name (`"CDA"`).

**Fix**
- Read a single constant (e.g. from `package.json` or `env`) and pass that to `wallet.enable(NAME)` in every project.

**Why it matters**: Gives users a recognisable permission prompt and avoids confusion if multiple dapps share the same identifier.

---

## 6. RPC Endpoint Resilience

**Problem**: Every chain is configured with only **one** RPC endpoint (Stakeworld).

**Fix**
- Provide a list of known-good providers (e.g. Parity, OnFinality, Dwellir) and implement simple fail-over (try next endpoint on WebSocket error).

**Why it matters**: Keeps the dapp functional when an RPC goes down without waiting for a redeploy.

---

## 7. Minor UX Polish

| Area | Suggestion |
| --- | --- |
| HTML `<title>` | Replace template defaults ("Vite + React + TS", etc.) with project name. |
| Local Storage | Persist **only** `extensionName` and `account.address` instead of serialising the full wallet object. |
| Connect Modal | Stop `onClick` at card root when the *Connect* button is disabled (prevents accidental connect calls). |

---

## Project-specific Notes

| Template | Extras |
| --- | --- |
| **React + PAPI** | Ensure `client.blocks$` subscription is disposed in `useEffect` cleanup. |
| **Vue + Dedot** | Add `onUnmounted` cleanup for `system.events` listener; use `ref` + `watchEffect` if the chain can change. |
| **Vue + PAPI** | Same as React + PAPI: keep the `.unsubscribe()` reference for blocks and transactions. |
