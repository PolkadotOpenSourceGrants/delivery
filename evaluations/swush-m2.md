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
