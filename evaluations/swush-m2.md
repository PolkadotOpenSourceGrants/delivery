# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/swush-dex-aggregator.md
- **Milestone:** 2


| Number | Deliverable | Accepted | Link | Notes |
|--------|-------------|------|-------|-------|
| 0a. | License | <ul><li>[x] </li></ul> | [AGPL v3](https://github.com/swush-labs/swush-app/blob/swush-new-ui/LICENSE) | |
| 0b. | Documentation | <ul><li>[x] </li></ul> | [README](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md) | Decent docs |
| 0c. | Testing and Testing Guide | <ul><li>[x] </li></ul> | [Setup Guide](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md#getting-started) | All passing |
| 0e. | Article | <ul><li>[x] </li></ul> | [Chainflip Implementation Summary](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/IMPLEMENTATION_SUMMARY.md), [Hyperliquid Integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/HYPERLIQUID_INTEGRATION.md), [Solana integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/SOLANA_INTEGRATION_SUMMARY.md) |  |
| 1. | User analytics | <ul><li>[x] </li></ul> | [SwapHistoryDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapHistoryDialog.tsx), [SwapHistoryItem](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/ui/SwapHistoryItem.tsx), [db schema](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/db/schema.ts) | Works as expected |
| 2. | Currency dollar value | <ul><li>[x] </li></ul> | [CoinGecko service](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/prices/coingeckoService.ts) | Works as expected |
| 3. | Currency metadata rendering | <ul><li>[x] </li></ul> | [Asset registry](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/assetRegistry.ts), [useAssetAggregator](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/useAssetAggregator.ts) | Works as expected |
| 4. | User XP Points | <ul><li>[x] </li></ul> | [SwapCompleteDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | Works as expected |
| 5. | Ethereum EVM and Solana support | <ul><li>[x] </li></ul> | [Kheopskit config](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/lib/config/kheopskit.ts), [use-selected-account](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/wallet/use-selected-account.ts) | Works as expected |
| 6. | Chainflip integration (Arbitrum and Solana) | <ul><li>[x] </li></ul> | [Chainflip client](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/client.ts), [useChainflipRoute](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipRoute.ts), [useChainflipExecution](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipExecution.ts), [signerUtils](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/signerUtils.ts) | Works as expected |
| 7. | Hyperliquid referral on-ramp | <ul><li>[x] </li></ul> | [SwapCompleteDialog – Hyperliquid CTA](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | Works as expected |

# General Notes

## UI

Routing works nicely across different chains. Very similar to 1inch.

<img width="455" height="756" alt="router" src="https://github.com/user-attachments/assets/e60badc1-7ad7-4e05-9c41-0102c655fbcb" />

## Testing

All unit tests passing (with a depreceation warnings):

<details>
  <summary>Output</summary>

```ts
pnpm test

> swush-me@0.1.0 test /home/ubuntu/swush-app
> pnpm --filter @swush/web test


> @swush/web@0.1.0 test /home/ubuntu/swush-app/apps/web
> jest

 PASS  src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts
  ● Console

    console.error
      Warning: `ReactDOMTestUtils.act` is deprecated in favor of `React.act`. Import `act` from `react` instead of `react-dom/test-utils`. See https://react.dev/warnings/react-dom-test-utils for more info.

      44 |
      45 |   it('should validate required parameters', async () => {
    > 46 |     const { result } = renderHook(() =>
         |                                  ^
      47 |       useXcmSwapExecution({
      48 |         inputToken: null,
      49 |         outputToken: null,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:71:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:45:7)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1736:7)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:46:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      44 |
      45 |   it('should validate required parameters', async () => {
    > 46 |     const { result } = renderHook(() =>
         |                                  ^
      47 |       useXcmSwapExecution({
      48 |         inputToken: null,
      49 |         outputToken: null,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:46:34)

    console.error
      Warning: unmountComponentAtNode is deprecated and will be removed in the next major release. Switch to the createRoot API. Learn more: https://reactjs.org/link/switch-to-createroot

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.unmountComponentAtNode (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29754:7)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:92:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at unmount (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:91:26)
      at unmountHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:123:7)
      at cleanup (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:14:11)
      at Object.<anonymous> (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:42:13)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      72 |
      73 |   it('should validate input amount', async () => {
    > 74 |     const { result } = renderHook(() =>
         |                                  ^
      75 |       useXcmSwapExecution({
      76 |         inputToken: mockInputToken,
      77 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:74:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      100 |
      101 |   it('should validate negative input amount', async () => {
    > 102 |     const { result } = renderHook(() =>
          |                                  ^
      103 |       useXcmSwapExecution({
      104 |         inputToken: mockInputToken,
      105 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:102:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      129 |     const invalidToken = { ...mockInputToken, assetKey: undefined };
      130 |
    > 131 |     const { result } = renderHook(() =>
          |                                  ^
      132 |       useXcmSwapExecution({
      133 |         inputToken: invalidToken as any,
      134 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:131:34)

    console.error
      ❌ Input token configuration error: {
        id: 'DOT-native-Polkadot',
        symbol: 'DOT',
        name: 'Polkadot',
        icon: 'D',
        decimals: 10,
        assetKey: undefined,
        networkChain: 'Polkadot'
      }

      273 |     // Ensure tokens have required XCM fields
      274 |     if (!inputToken.assetKey || !inputToken.networkChain) {
    > 275 |       console.error('❌ Input token configuration error:', inputToken);
          |               ^
      276 |       const errorDetails: ErrorDetails = {
      277 |         message: 'Input token missing assetKey or networkChain',
      278 |         code: 'INVALID_TOKEN_CONFIG'

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at Object.error [as executeSwap] (src/components/swap/hooks/useXcmSwapExecution.ts:275:15)
      at executeSwap (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:147:28)
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:146:14)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      159 |     const invalidToken = { ...mockOutputToken, networkChain: undefined };
      160 |
    > 161 |     const { result } = renderHook(() =>
          |                                  ^
      162 |       useXcmSwapExecution({
      163 |         inputToken: mockInputToken,
      164 |         outputToken: invalidToken as any,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:161:34)

    console.error
      ❌ Output token configuration error: {
        id: 'USDC-1337-AssetHubPolkadot',
        symbol: 'USDC',
        name: 'USD Coin',
        icon: 'U',
        decimals: 6,
        assetKey: 'USDC-1337-AssetHubPolkadot',
        networkChain: undefined
      }

      283 |
      284 |     if (!outputToken.assetKey || !outputToken.networkChain) {
    > 285 |       console.error('❌ Output token configuration error:', outputToken);
          |               ^
      286 |       const errorDetails: ErrorDetails = {
      287 |         message: 'Output token missing assetKey or networkChain',
      288 |         code: 'INVALID_TOKEN_CONFIG'

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at Object.error [as executeSwap] (src/components/swap/hooks/useXcmSwapExecution.ts:285:15)
      at executeSwap (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:177:28)
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:176:14)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      187 |
      188 |   it('should return executeSwap function', () => {
    > 189 |     const { result } = renderHook(() =>
          |                                  ^
      190 |       useXcmSwapExecution({
      191 |         inputToken: mockInputToken,
      192 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmSwapExecution.test.ts:189:34)

 PASS  src/components/swap/hooks/__tests__/useXcmRoute.test.ts
  ● Console

    console.error
      Warning: `ReactDOMTestUtils.act` is deprecated in favor of `React.act`. Import `act` from `react` instead of `react-dom/test-utils`. See https://react.dev/warnings/react-dom-test-utils for more info.

      56 |   it('should initialize with empty state', () => {
      57 |     process.env.NEXT_PUBLIC_SKIP_PRICE_FETCH = 'true';
    > 58 |     const { result } = renderHook(() =>
         |                                  ^
      59 |       useXcmRoute({
      60 |         inputToken: null,
      61 |         outputToken: null,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:71:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:45:7)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1736:7)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:58:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      56 |   it('should initialize with empty state', () => {
      57 |     process.env.NEXT_PUBLIC_SKIP_PRICE_FETCH = 'true';
    > 58 |     const { result } = renderHook(() =>
         |                                  ^
      59 |       useXcmRoute({
      60 |         inputToken: null,
      61 |         outputToken: null,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:58:34)

    console.error
      Warning: unmountComponentAtNode is deprecated and will be removed in the next major release. Switch to the createRoot API. Learn more: https://reactjs.org/link/switch-to-createroot

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.unmountComponentAtNode (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29754:7)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:92:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at unmount (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:91:26)
      at unmountHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:123:7)
      at cleanup (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:14:11)
      at Object.<anonymous> (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:42:13)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      74 |   it('should skip price fetch when skipPriceFetch is true', async () => {
      75 |     process.env.NEXT_PUBLIC_SKIP_PRICE_FETCH = 'true';
    > 76 |     const { result } = renderHook(() =>
         |                                  ^
      77 |       useXcmRoute({
      78 |         inputToken: mockInputToken,
      79 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:76:34)

    console.log
      ⏭️ Skipping price fetch (skipPriceFetch=true)

      at log (src/components/swap/hooks/useXcmRoute.ts:150:15)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

       98 |     const invalidToken = { ...mockInputToken, assetKey: undefined };
       99 |     
    > 100 |     const { result } = renderHook(() =>
          |                                  ^
      101 |       useXcmRoute({
      102 |         inputToken: invalidToken as any,
      103 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:100:34)

    console.error
      ❌ Input token missing assetKey or networkChain: {
        id: 'DOT-native-Polkadot',
        symbol: 'DOT',
        name: 'Polkadot',
        icon: 'D',
        decimals: 10,
        assetKey: undefined,
        networkChain: 'Polkadot'
      }

      182 |     // Ensure tokens have required XCM fields
      183 |     if (!inputToken.assetKey || !inputToken.networkChain) {
    > 184 |       console.error('❌ Input token missing assetKey or networkChain:', inputToken);
          |               ^
      185 |       setRouteState({
      186 |         isLoading: false,
      187 |         error: 'Input token configuration error',

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at error (src/components/swap/hooks/useXcmRoute.ts:184:15)
      at fetchRoute (src/components/swap/hooks/useXcmRoute.ts:454:11)
      at Object.fn [as debouncedFetchRoute] (jest.setup.js:107:38)
      at debouncedFetchRoute (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:111:22)
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:110:14)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      119 |   it('should reset route state correctly', () => {
      120 |     process.env.NEXT_PUBLIC_SKIP_PRICE_FETCH = 'true';
    > 121 |     const { result } = renderHook(() =>
          |                                  ^
      122 |       useXcmRoute({
      123 |         inputToken: mockInputToken,
      124 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:121:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      141 |   it('should handle separate loading states for quote and fees', () => {
      142 |     process.env.NEXT_PUBLIC_SKIP_PRICE_FETCH = 'true';
    > 143 |     const { result } = renderHook(() =>
          |                                  ^
      144 |       useXcmRoute({
      145 |         inputToken: mockInputToken,
      146 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:143:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      157 |   it('should clear state for invalid amounts', async () => {
      158 |     process.env.NEXT_PUBLIC_SKIP_PRICE_FETCH = 'true';
    > 159 |     const { result } = renderHook(() =>
          |                                  ^
      160 |       useXcmRoute({
      161 |         inputToken: mockInputToken,
      162 |         outputToken: mockOutputToken,

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmRoute.test.ts:159:34)

 PASS  src/services/xcm-router/__tests__/feeCalculator.test.ts
 PASS  src/components/swap/hooks/__tests__/useXcmTokens.test.ts
  ● Console

    console.error
      Warning: `ReactDOMTestUtils.act` is deprecated in favor of `React.act`. Import `act` from `react` instead of `react-dom/test-utils`. See https://react.dev/warnings/react-dom-test-utils for more info.

      120 | describe('useXcmTokens - Phase 1: Token Selection', () => {
      121 |   it('should generate correct asset key format for native tokens', () => {
    > 122 |     const { result } = renderHook(() => useXcmTokens());
          |                                  ^
      123 |     
      124 |     const dotToken = result.current.fromTokens.find(t => t.symbol === 'DOT');
      125 |     expect(dotToken?.assetKey).toBe('DOT-native-Polkadot');

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:71:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:45:7)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1736:7)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmTokens.test.ts:122:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      120 | describe('useXcmTokens - Phase 1: Token Selection', () => {
      121 |   it('should generate correct asset key format for native tokens', () => {
    > 122 |     const { result } = renderHook(() => useXcmTokens());
          |                                  ^
      123 |     
      124 |     const dotToken = result.current.fromTokens.find(t => t.symbol === 'DOT');
      125 |     expect(dotToken?.assetKey).toBe('DOT-native-Polkadot');

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmTokens.test.ts:122:34)

    console.error
      Warning: unmountComponentAtNode is deprecated and will be removed in the next major release. Switch to the createRoot API. Learn more: https://reactjs.org/link/switch-to-createroot

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.unmountComponentAtNode (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29754:7)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:92:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at unmount (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:91:26)
      at unmountHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:123:7)
      at cleanup (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:14:11)
      at Object.<anonymous> (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:42:13)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      128 |
      129 |   it('should generate correct asset key format for asset tokens', () => {
    > 130 |     const { result } = renderHook(() => useXcmTokens());
          |                                  ^
      131 |     
      132 |     const usdcToken = result.current.toTokens.find(t => t.symbol === 'USDC');
      133 |     expect(usdcToken?.assetKey).toBe('USDC-1337-AssetHubPolkadot');

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmTokens.test.ts:130:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      136 |
      137 |   it('should provide separate from/to token lists', () => {
    > 138 |     const { result } = renderHook(() => useXcmTokens());
          |                                  ^
      139 |     
      140 |     expect(result.current.fromTokens).toBeDefined();
      141 |     expect(result.current.toTokens).toBeDefined();

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmTokens.test.ts:138:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      145 |
      146 |   it('should convert UnifiedAsset to TokenInfo with all required fields', () => {
    > 147 |     const { result } = renderHook(() => useXcmTokens());
          |                                  ^
      148 |     
      149 |     const token = result.current.fromTokens[0];
      150 |     expect(token).toHaveProperty('id');

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmTokens.test.ts:147:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      158 |
      159 |   it('should track initial loading state correctly', () => {
    > 160 |     const { result } = renderHook(() => useXcmTokens());
          |                                  ^
      161 |     
      162 |     // With mocked data, should not be loading
      163 |     expect(result.current.isInitialLoad).toBe(false);

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/components/swap/hooks/__tests__/useXcmTokens.test.ts:160:34)

 PASS  src/services/xcm-router/__tests__/useCurrencyOptions.test.ts
  ● Console

    console.error
      Warning: `ReactDOMTestUtils.act` is deprecated in favor of `React.act`. Import `act` from `react` instead of `react-dom/test-utils`. See https://react.dev/warnings/react-dom-test-utils for more info.

      33 | describe('useCurrencyOptions - Asset Key Format', () => {
      34 |   it('should generate correct key format with network suffix', () => {
    > 35 |     const { result } = renderHook(() =>
         |                                  ^
      36 |       useCurrencyOptions(
      37 |         'Polkadot' as any,
      38 |         ['HydrationDex'],

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:71:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:45:7)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1736:7)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/services/xcm-router/__tests__/useCurrencyOptions.test.ts:35:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      33 | describe('useCurrencyOptions - Asset Key Format', () => {
      34 |   it('should generate correct key format with network suffix', () => {
    > 35 |     const { result } = renderHook(() =>
         |                                  ^
      36 |       useCurrencyOptions(
      37 |         'Polkadot' as any,
      38 |         ['HydrationDex'],

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/services/xcm-router/__tests__/useCurrencyOptions.test.ts:35:34)

    console.error
      Warning: unmountComponentAtNode is deprecated and will be removed in the next major release. Switch to the createRoot API. Learn more: https://reactjs.org/link/switch-to-createroot

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.unmountComponentAtNode (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29754:7)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:92:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at unmount (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:91:26)
      at unmountHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:123:7)
      at cleanup (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:14:11)
      at Object.<anonymous> (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/cleanup.js:42:13)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      50 |
      51 |   it('should use "native" keyword for native tokens', () => {
    > 52 |     const { result } = renderHook(() =>
         |                                  ^
      53 |       useCurrencyOptions(
      54 |         'Polkadot' as any,
      55 |         ['HydrationDex'],

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/services/xcm-router/__tests__/useCurrencyOptions.test.ts:52:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      66 |
      67 |   it('should use assetId for asset tokens', () => {
    > 68 |     const { result } = renderHook(() =>
         |                                  ^
      69 |       useCurrencyOptions(
      70 |         'Polkadot' as any,
      71 |         ['HydrationDex'],

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/services/xcm-router/__tests__/useCurrencyOptions.test.ts:68:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

      82 |
      83 |   it('should create both from and to currency maps', () => {
    > 84 |     const { result } = renderHook(() =>
         |                                  ^
      85 |       useCurrencyOptions(
      86 |         'Polkadot' as any,
      87 |         ['HydrationDex'],

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/services/xcm-router/__tests__/useCurrencyOptions.test.ts:84:34)

    console.error
      Warning: ReactDOM.render is no longer supported in React 18. Use createRoot instead. Until you switch to the new API, your app will behave as if it's running React 17. Learn more: https://reactjs.org/link/switch-to-createroot

       98 |
       99 |   it('should create select options with proper labels', () => {
    > 100 |     const { result } = renderHook(() =>
          |                                  ^
      101 |       useCurrencyOptions(
      102 |         'Polkadot' as any,
      103 |         ['HydrationDex'],

      at console.error (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/console.js:19:7)
      at printWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:86:30)
      at error (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:60:7)
      at Object.render (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom.development.js:29716:5)
      at ../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:80:18
      at act (../../node_modules/.pnpm/react@18.3.1/node_modules/react/cjs/react.development.js:2512:16)
      at actWithWarning (../../node_modules/.pnpm/react-dom@18.3.1_react@18.3.1/node_modules/react-dom/cjs/react-dom-test-utils.development.js:1740:10)
      at render (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/dom/pure.js:79:26)
      at renderHook (../../node_modules/.pnpm/@testing-library+react-hooks@8.0.1_@types+react@18.3.18_react-dom@18.3.1_react@18.3.1__react@18.3.1/node_modules/@testing-library/react-hooks/lib/core/index.js:114:5)
      at Object.<anonymous> (src/services/xcm-router/__tests__/useCurrencyOptions.test.ts:100:34)

 PASS  src/components/swap/hooks/__tests__/utils.test.ts

Test Suites: 6 passed, 6 total
Tests:       53 passed, 53 total
Snapshots:   0 total
Time:        1.32 s
Ran all test suites.
```
</details>
