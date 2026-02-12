# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/swush-dex-aggregator.md
- **Milestone:** 2




| Number | Deliverable | Link | Notes |
|--------|-------------|------|-------|
| 0a. | License | [AGPL v3](https://github.com/swush-labs/swush-app/blob/swush-new-ui/LICENSE) | |
| 0b. | Documentation | [README](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md) | |
| 0c. | Testing and Testing Guide | [Setup Guide](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md#getting-started) | Steps to setup the project and run the tests.|
| 0e. | Article | [Chainflip Implementation Summary](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/IMPLEMENTATION_SUMMARY.md), [Hyperliquid Integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/HYPERLIQUID_INTEGRATION.md), [Solana integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/docs/chainflip/SOLANA_INTEGRATION_SUMMARY.md) |  |
| 1. | User analytics | [SwapHistoryDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapHistoryDialog.tsx), [SwapHistoryItem](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/ui/SwapHistoryItem.tsx), [db schema](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/db/schema.ts) |  |
| 2. | Currency dollar value | [CoinGecko service](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/prices/coingeckoService.ts) |  |
| 3. | Currency metadata rendering | [Asset registry](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/assetRegistry.ts), [useAssetAggregator](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/xcm-router/useAssetAggregator.ts) |  |
| 4. | User XP Points | [SwapCompleteDialog](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) |  |
| 5. | Ethereum EVM and Solana support | [Kheopskit config](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/lib/config/kheopskit.ts), [use-selected-account](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/wallet/use-selected-account.ts) |  |
| 6. | Chainflip integration (Arbitrum and Solana) | [Chainflip client](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/client.ts), [useChainflipRoute](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipRoute.ts), [useChainflipExecution](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useChainflipExecution.ts), [signerUtils](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/services/chainflip/signerUtils.ts) |  |
| 7. | Hyperliquid referral on-ramp | [SwapCompleteDialog – Hyperliquid CTA](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/ui/SwapCompleteDialog.tsx) | |

# General Notes
