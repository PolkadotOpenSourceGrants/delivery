# Milestone Delivery :mailbox:


**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Swush Dex Aggregator](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/swush-dex-aggregator.md)
* **Milestone Number:** 2
* **DOT Payment Address:** 124C7vfXbvBausfviN3ydZjj4voxPyEwmnJDuNJ9y4kU3ETN
  - **On-chain identity**: muddlebee/coreblocks-multisig



**Context** 

Milestone 2: External chain integration via Chainflip for cross-ecosystem swaps (Asset Hub DOT/USDC/USDT to Arbitrum and Solana), extended EVM and Solana wallet support, user analytics and swap history with XP points, USD valuation of assets, currency metadata in the UI, and a Hyperliquid referral on-ramp after swaps to USDC on Arbitrum.



**Instructions before testing the deliverables**

- Setup all the wallet apps required for testing
  - Metamask for Ethereum
  - Phantom for Solana
  - Polkadot.js for Polkadot

- All the wallets should be connected from Source side to be able to use in Receiver side.

Note : Test accounts shared via email.

**Github repo**  

https://github.com/swush-labs/swush-app



| Number | Deliverable | Link | Notes |
|--------|-------------|------|-------|
| 0a. | License | [AGPL v3](https://github.com/swush-labs/swush-app/blob/swush-new-ui/LICENSE) | |
| 0b. | Documentation | [README](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md) | |
| 0c. | Testing and Testing Guide | [Setup Guide](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md#getting-started) | Steps to setup the project and run the tests.|
| 0e. | Article | [Chainflip Implementation Summary](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/IMPLEMENTATION_SUMMARY.md), [Hyperliquid Integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/HYPERLIQUID_INTEGRATION.md), [Solana integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/SOLANA_INTEGRATION_SUMMARY.md) | Documentation of M2 features. |
| 1. | User analytics | [SwapHistoryDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapHistoryDialog.tsx), [SwapHistoryItem](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/ui/SwapHistoryItem.tsx), [db schema](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/db/schema.ts) | Swap/transaction history and XP tracking. |
| 2. | Currency dollar value | [CoinGecko service](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/prices/coingeckoService.ts) | USD value of assets in the UI. |
| 3. | Currency metadata rendering | [Asset registry](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/assetRegistry.ts), [useAssetAggregator](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/useAssetAggregator.ts) | Metadata for the assets. |
| 4. | User XP Points | [SwapCompleteDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | Points awarded post-swap. |
| 5. | Ethereum EVM and Solana support | [Kheopskit config](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/lib/config/kheopskit.ts), [use-selected-account](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/wallet/use-selected-account.ts) | Arbitrum/Ethereum and Solana wallet support. |
| 6. | Chainflip integration (Arbitrum and Solana) | [Chainflip client](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/client.ts), [useChainflipRoute](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipRoute.ts), [useChainflipExecution](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipExecution.ts), [signerUtils](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/signerUtils.ts) | Cross-ecosystem swaps with fee estimation, slippage protection, status tracking. |
| 7. | Hyperliquid referral on-ramp | [SwapCompleteDialog – Hyperliquid CTA](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | One-click CTA to Hyperliquid with referral after DOT/USDC/USDT → Arbitrum (Chainflip). User can deposit supported assets directly into Hyperliquid after the swap.|


**Additional Information**  

A demo and walkthrough of the web app 

- [Milestone 2 Demo](https://www.loom.com/share/b45fdbb656ae4b58af8a58bdc6ae3987)
- [Analytics and Alternative Routes](https://www.loom.com/share/9a13137b91ec4c219cc25fcdacdbb5ec)


**Testing Instructions**

I have shared the route links below used in the demo video.

- Swap from Polkadot Asset Hub Testnet(Perseverance) - DOT to Arbitrum testnet(Sepolia) - USDC

[http://localhost:3000/?fromNetwork=AssetHubPerseverance&toNetwork=Arbitrum+Sepolia](http://localhost:3000/?fromNetwork=AssetHubPerseverance&toNetwork=Arbitrum+Sepolia)

- Swap from Ethereum testnet(Sepolia) - USDC to Solana testnet(Devnet) - SOL

[http://localhost:3000/?fromNetwork=Sepolia&toNetwork=SolanaDevnet&from=USDC&to=SOL](http://localhost:3000/?fromNetwork=Sepolia&toNetwork=SolanaDevnet&from=USDC&to=SOL)
