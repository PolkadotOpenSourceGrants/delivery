# Milestone Delivery :mailbox:


**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [Swush Dex Aggregator](https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/swush-dex-aggregator.md)
* **Milestone Number:** e.g. 1
* **DOT Payment Address:** Please provide the payment beneficiary address

**Context** 

Milestone 1: Cross-chain asset swaps between Asset Hub, Hydration, Moonbeam, Bifrost finding the best rate and asset route comparing various DEXes like AssetHub, Hydration, Bifrost and Acala DEX with multi-wallet connectivity and fee estimation.


**Deliverables**
- We are using Chopsticks for multi-network simulation to test the core functionality and transactions.
- Fewer assets like DOT, USDC, USDT are enabled right now for testing purposes.
- Network and assets are config based and can be easily extended to add more networks and assets.
- Paraspell SDK is used for transaction purposes, including submitting the transaction to the network, tracking the transaction status, dry run transaction and slippage protection.

**Instructions before testing the deliverables**
- Ensure chopsticks is running, post `pnpm dev:all`
- Setup the [demo wallet](https://github.com/swush-labs/swush-app/blob/swush-new-ui/packages/chopsticks/test-wallet/test-wallet-setup.md) with instructions in the link configured for chopsticks with balances for testing.


| Number | Deliverable | Link | Notes |
|--------|-------------|------|-------|
| 0a. | License | AGPL v3 | |
| 0b. | Documentation | [README](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md) | |
| 0c. | Testing and Testing Guide | [Unit Tests](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md#unit-tests) | |
| 1. | Core router: cross chain swaps | [Core Router](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts) | Core router is used to execute the swap with multiple hops with best rate and asset route across different chains and DEXes. |
| 2. | Transaction tracker | [Transaction Tracker](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts#L366-L445) | Transaction status is tracked and updated in the UI. |
| 3. | Route selector and Total Fee Estimation | [Route Selector](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmRoute.ts) | Route selector is used to select the best route for the swap and total fee estimation across different chains and DEXes. |
| 4. | Multi-wallet enablement | [Multi-wallet Enablement](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts) | Wallet library to support both Substrate and EVM-based wallets.|
| 5. | Multi-network connection | [Multi-network Connection](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/wallet) | Chopsticks is used for multi-network connection across parachains Bifrost, Hydration, Moonbeam, Asset Hub and Acala and the RPCs are configurable in code. |
| 6. | Transaction dry run | [Paraspell SDK Integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts#L366-L483) | Paraspell SDK handles the transaction dry run if any error occurs, it will be shown to the user and the transaction will not be executed. |
| 7. | Slippage protection | [Slippage storage](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/utils/slippageStorage.ts) | Slippage protection is implemented to check if the output amount is within the acceptable range and user can confirm the transaction in confirmation modal. |


