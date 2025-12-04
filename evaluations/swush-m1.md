# Evaluation

- **Status:** In progress
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/swush-dex-aggregator.md
- **Milestone:** 1

| Number | Deliverable | Accepted | Link | Notes |
|--------|-------------|------|-------|-----------|
| 0a. | License | <ul><li>[x] </li></ul> | AGPL v3 | |
| 0b. | Documentation | <ul><li>[x] </li></ul> | [README](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md) | |
| 0c. | Testing and Testing Guide | <ul><li>[x] </li></ul> | [Setup Guide](https://github.com/swush-labs/swush-app/blob/swush-new-ui/README.md#getting-started) | |
| 1. | Core router: cross chain swaps | <ul><li>[x] </li></ul> | [Core Router](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts) | |
| 2. | Transaction tracker | <ul><li>[x] </li></ul> | [Transaction Tracker](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts#L366-L445) |  |
| 3. | Route selector and Total Fee Estimation | <ul><li>[x] </li></ul> | [Route Selector](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmRoute.ts) | | 
| 4. | Multi-wallet enablement | <ul><li>[x] </li></ul> | [Multi-wallet Enablement](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/wallet) | |
| 5. | Multi-network connection | <ul><li>[x] </li></ul> | [Multi-network Connection](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts#L332-L446) |  |
| 6. | Transaction dry run | <ul><li>[x] </li></ul> | [Paraspell SDK Integration](https://github.com/swush-labs/swush-app/blob/swush-new-ui/apps/web/src/components/swap/hooks/useXcmSwapExecution.ts#L366-L483) |  |
| 7. | Slippage protection | <ul><li>[x] </li></ul> | [Slippage storage](https://github.com/swush-labs/swush-me-app/blob/swush-new-ui/apps/web/src/components/swap/utils/slippageStorage.ts) |  |

# General Notes

`pnp dev:all` properly compiles and spins up Chopsticks:

<details>
  <summary>Output</summary>

```ts
pnpm dev:all

> swush-me@0.1.0 dev:all /home/ubuntu/swush-app
> pnpm dev & pnpm start-chopsticks


> swush-me@0.1.0 dev /home/ubuntu/swush-app
> pnpm --filter @swush/web dev


> swush-me@0.1.0 start-chopsticks /home/ubuntu/swush-app
> npx @acala-network/chopsticks@latest xcm -p packages/chopsticks/config/polkadot_asset_hub.yml -p packages/chopsticks/config/hydration.yml -p packages/chopsticks/config/bifrost.yml -p packages/chopsticks/config/acala.yml

⠴
> @swush/web@0.1.0 dev /home/ubuntu/swush-app/apps/web
> next dev

⠦  ▲ Next.js 14.2.15
  - Local:        http://localhost:3000
  - Environments: .env.local, .env
  - Experiments (use with caution):
    · esmExternals

 ✓ Starting...
⠧ ✓ Ready in 1918ms
Need to install the following packages:
@acala-network/chopsticks@1.2.5
Ok to proceed? (y) y

npm warn deprecated @npmcli/move-file@1.1.2: This functionality has been moved to @npmcli/fs
npm warn deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm warn deprecated rimraf@3.0.2: Rimraf versions prior to v4 are no longer supported
npm warn deprecated npmlog@6.0.2: This package is no longer supported.
npm warn deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
npm warn deprecated are-we-there-yet@3.0.1: This package is no longer supported.
npm warn deprecated gauge@4.0.4: This package is no longer supported.
npm warn deprecated boolean@3.2.0: Package no longer supported. Contact Support at https://www.npmjs.com/support for more info.
npm warn deprecated node-domexception@1.0.0: Use your platform's native DOMException instead
npm warn deprecated @substrate/connect@0.8.11: versions below 1.x are no longer maintained
        chopsticks::executor  TRACE: [0] Calling Metadata_metadata
[23:08:24.210] INFO: Polkadot Asset Hub RPC listening on http://[::]:3421 and ws://[::]:3421
    app: "chopsticks"
        chopsticks::executor  TRACE: [1] Calling Metadata_metadata
[23:08:26.874] INFO: Hydration RPC listening on http://[::]:3422 and ws://[::]:3422
    app: "chopsticks"
        chopsticks::executor  TRACE: [2] Calling Metadata_metadata
[23:08:28.787] INFO: Bifrost Polkadot RPC listening on http://[::]:3423 and ws://[::]:3423
    app: "chopsticks"
        chopsticks::executor  TRACE: [3] Calling Metadata_metadata
[23:08:30.686] INFO: Acala RPC listening on http://[::]:3424 and ws://[::]:3424
    app: "chopsticks"
[23:08:30.985] INFO (xcm): Connected parachains [1000,2000,2030,2034]
    app: "chopsticks"
[23:08:31.302] INFO (block-builder): Acala building #9,998,212
    app: "chopsticks"
    number: 9998212
    extrinsics: []
    umpCount: 0
[23:08:31.763] INFO (block-builder): Bifrost Polkadot building #10,216,554
    app: "chopsticks"
    number: 10216554
    extrinsics: []
    umpCount: 0
        chopsticks::executor  TRACE: [6] Calling Core_initialize_block
        chopsticks::executor  TRACE: [7] Calling Core_initialize_block
        chopsticks::executor  TRACE: [6] Completed Core_initialize_block
        chopsticks::executor  TRACE: [8] Calling BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [8] Completed BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [9] Calling BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [10] Calling BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [9] Completed BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [11] Calling BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [10] Completed BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [12] Calling BlockBuilder_finalize_block
        chopsticks::executor  TRACE: [11] Completed BlockBuilder_apply_extrinsic
        chopsticks::executor  TRACE: [13] Calling BlockBuilder_finalize_block
        chopsticks::executor  TRACE: [12] Completed BlockBuilder_finalize_block
        chopsticks::executor  TRACE: [13] Completed BlockBuilder_finalize_block
[23:08:36.880] INFO (block-builder): Acala new head #9,998,212
    app: "chopsticks"
    number: 9998212
    hash: "0x3c338c2be45f9f68b19bd399010b0c889681378b54419ded19ec179f07553ea2"
    extrinsics: []
    pendingExtrinsics: []
    ump: {}
[23:08:36.881] INFO (xcm): outboundHrmpMessage
    app: "chopsticks"
    outboundHrmpMessage: []
[23:08:37.824] INFO (block-builder): Bifrost Polkadot new head #10,216,554
    app: "chopsticks"
    number: 10216554
    hash: "0xb93a2996e07cba495b96acdff369d252164f0ac75a30037dab7223744342a04c"
    extrinsics: []
    pendingExtrinsics: []
    ump: {}
[23:08:37.825] INFO (xcm): outboundHrmpMessage
    app: "chopsticks"
    outboundHrmpMessage: []
```
</details>

I'm able to run the app in my browser locally. Everything works really well, can connect and swap between Hydration, BiFrost, and Asset Hub.

<img width="516" height="594" alt="swush" src="https://github.com/user-attachments/assets/7c27356c-63af-4ed9-a22c-4f5e184d2aa5" />

## Testing

Tests all passing:
```
Test Suites: 6 passed, 6 total
Tests:       53 passed, 53 total
Snapshots:   0 total
Time:        6.133 s
Ran all test suites.
```
