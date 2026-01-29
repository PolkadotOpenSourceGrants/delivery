# Milestone Delivery :mailbox:


**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Swush Dex Aggregator](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/swush-dex-aggregator.md)
* **Milestone Number:** 2
* **DOT Payment Address:** 124C7vfXbvBausfviN3ydZjj4voxPyEwmnJDuNJ9y4kU3ETN
  - **On-chain identity**: muddlebee/coreblocks-multisig



**Context** 

Milestone 2: External chain integration via Chainflip for cross-ecosystem swaps (Asset Hub DOT/USDC/USDT to Arbitrum and Solana), extended EVM and Solana wallet support, user analytics and swap history with XP points, USD valuation of assets, currency metadata in the UI, and a Hyperliquid referral on-ramp after swaps to USDC on Arbitrum.



**Instructions before testing the deliverables**

- Setup all the test wallets
  - Metamask for Ethereum
  - Phantom for Solana
  - Polkadot.js for Polkadot


**Github repo**  

https://github.com/swush-labs/swush-app



| Number | Deliverable | Link | Notes |
|--------|-------------|------|-------|
| 0a. | License | [AGPL v3](https://github.com/swush-labs/swush-app/blob/swush-new-ui/LICENSE) | |
| 0b. | Documentation | [README](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md), [Chainflip integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/IMPLEMENTATION_SUMMARY.md), [Hyperliquid guide](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/HYPERLIQUID_INTEGRATION.md) | Inline docs and tutorials for cross-ecosystem routing and Hyperliquid. |
| 0c. | Testing and Testing Guide | [README – Getting started](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md#getting-started), [Test summary](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/new-ui/TEST_SUMMARY.md) | Setup, `pnpm test` |
| 0e. | Article | [Chainflip Implementation Summary](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/IMPLEMENTATION_SUMMARY.md), [Hyperliquid Integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/HYPERLIQUID_INTEGRATION.md), [Solana integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/SOLANA_INTEGRATION_SUMMARY.md) | Documentation of M2 features. |
| 1. | User analytics | [SwapHistoryDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapHistoryDialog.tsx), [SwapHistoryItem](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/ui/SwapHistoryItem.tsx), [db schema](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/db/schema.ts) | Swap/transaction history and XP tracking across chains. |
| 2. | Currency dollar value | [CoinGecko service](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/prices/coingeckoService.ts) | USD valuation of assets in the UI. |
| 3. | Currency metadata rendering | [Asset registry](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/assetRegistry.ts), [useAssetAggregator](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/useAssetAggregator.ts) | Logos, names, symbols, decimals per chain. |
| 4. | User XP Points | [SwapCompleteDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | Points awarded post-swap with reveal; levels on more points. |
| 5. | Ethereum EVM and Solana support | [Kheopskit config](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/lib/config/kheopskit.ts), [use-selected-account](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/wallet/use-selected-account.ts) | Arbitrum/Ethereum and Solana wallet support. |
| 6. | Chainflip integration (Arbitrum and Solana) | [Chainflip client](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/client.ts), [useChainflipRoute](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipRoute.ts), [useChainflipExecution](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipExecution.ts), [signerUtils](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/signerUtils.ts) | Cross-ecosystem swaps with fee estimation, slippage protection, status tracking. |
| 7. | Hyperliquid referral on-ramp | [SwapCompleteDialog – Hyperliquid CTA](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | One-click CTA to Hyperliquid with referral after DOT/USDC/USDT → Arbitrum (Chainflip). |


**Additional Information**  

Chainflip routes (e.g. DOT → USDC on Arbitrum) require the Chainflip Testnet API key in env. 