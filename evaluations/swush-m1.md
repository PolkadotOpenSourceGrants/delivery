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

## Testing

A couple tests are failing in `blockchain` dir for pallets `pallet-fee-delegation` and `pallet-marketplace`. 

<details>
  <summary>Output</summary>

```ts
cargo test
⚡ Found 4 strongly connected components which includes at least one cycle each
cycle(001) ∈ α: DisputeCoordinator ~~{"DisputeDistributionMessage"}~~> DisputeDistribution ~~{"DisputeCoordinatorMessage"}~~>  *
cycle(002) ∈ β: ApprovalVoting ~~{"ApprovalDistributionMessage"}~~> ApprovalDistribution ~~{"ApprovalVotingMessage"}~~>  *
cycle(003) ∈ γ: CandidateBacking ~~{"CollatorProtocolMessage"}~~> CollatorProtocol ~~{"CandidateBackingMessage"}~~>  *
cycle(004) ∈ δ: NetworkBridgeRx ~~{"GossipSupportMessage"}~~> GossipSupport ~~{"NetworkBridgeRxMessage"}~~>  *
   Compiling frame-storage-access-test-runtime v0.4.0
   Compiling depow-runtime v0.1.0 (/home/ubuntu/DePow/blockchain/runtime)
error: failed to run custom build command for `frame-storage-access-test-runtime v0.4.0`

Caused by:
  process didn't exit successfully: `/home/ubuntu/DePow/blockchain/target/debug/build/frame-storage-access-test-runtime-320008f5e4af64ab/build-script-build` (exit status: 1)
  --- stderr
  Cannot compile the WASM runtime: the `wasm32-unknown-unknown` target is not installed!
  You can install it with `rustup target add wasm32-unknown-unknown --toolchain stable-x86_64-unknown-linux-gnu` if you're using `rustup`.
warning: build failed, waiting for other jobs to finish...
error: failed to run custom build command for `depow-runtime v0.1.0 (/home/ubuntu/DePow/blockchain/runtime)`

Caused by:
  process didn't exit successfully: `/home/ubuntu/DePow/blockchain/target/debug/build/depow-runtime-e90e322f885be996/build-script-build` (exit status: 1)
  --- stderr
  Cannot compile the WASM runtime: the `wasm32-unknown-unknown` target is not installed!
  You can install it with `rustup target add wasm32-unknown-unknown --toolchain stable-x86_64-unknown-linux-gnu` if you're using `rustup`.
rustup target add wasm32-unknown-unknown --toolchain stable-x86_64-unknown-linux-gnu
info: downloading component 'rust-std' for 'wasm32-unknown-unknown'
info: installing component 'rust-std' for 'wasm32-unknown-unknown'
 20.5 MiB /  20.5 MiB (100 %)   3.0 MiB/s in  6s         
cargo test
⚡ Found 4 strongly connected components which includes at least one cycle each
cycle(001) ∈ α: DisputeCoordinator ~~{"DisputeDistributionMessage"}~~> DisputeDistribution ~~{"DisputeCoordinatorMessage"}~~>  *
cycle(002) ∈ β: ApprovalVoting ~~{"ApprovalDistributionMessage"}~~> ApprovalDistribution ~~{"ApprovalVotingMessage"}~~>  *
cycle(003) ∈ γ: CandidateBacking ~~{"CollatorProtocolMessage"}~~> CollatorProtocol ~~{"CandidateBackingMessage"}~~>  *
cycle(004) ∈ δ: NetworkBridgeRx ~~{"GossipSupportMessage"}~~> GossipSupport ~~{"NetworkBridgeRxMessage"}~~>  *
   Compiling frame-storage-access-test-runtime v0.4.0
   Compiling depow-runtime v0.1.0 (/home/ubuntu/DePow/blockchain/runtime)
error: failed to run custom build command for `frame-storage-access-test-runtime v0.4.0`

Caused by:
  process didn't exit successfully: `/home/ubuntu/DePow/blockchain/target/debug/build/frame-storage-access-test-runtime-320008f5e4af64ab/build-script-build` (exit status: 1)
  --- stderr
  Cannot compile the WASM runtime: no standard library sources found at /home/ubuntu/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/src/rust!
  You can install them with `rustup component add rust-src --toolchain stable-x86_64-unknown-linux-gnu` if you're using `rustup`.
warning: build failed, waiting for other jobs to finish...
error: failed to run custom build command for `depow-runtime v0.1.0 (/home/ubuntu/DePow/blockchain/runtime)`

Caused by:
  process didn't exit successfully: `/home/ubuntu/DePow/blockchain/target/debug/build/depow-runtime-e90e322f885be996/build-script-build` (exit status: 1)
  --- stderr
  Cannot compile the WASM runtime: no standard library sources found at /home/ubuntu/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/src/rust!
  You can install them with `rustup component add rust-src --toolchain stable-x86_64-unknown-linux-gnu` if you're using `rustup`.
rustup component add rust-src --toolchain stable-x86_64-unknown-linux-gnu
info: downloading component 'rust-src'
info: installing component 'rust-src'
  3.3 MiB /   3.3 MiB (100 %)   1.9 MiB/s in  1s         
cargo test
⚡ Found 4 strongly connected components which includes at least one cycle each
cycle(001) ∈ α: DisputeCoordinator ~~{"DisputeDistributionMessage"}~~> DisputeDistribution ~~{"DisputeCoordinatorMessage"}~~>  *
cycle(002) ∈ β: ApprovalVoting ~~{"ApprovalDistributionMessage"}~~> ApprovalDistribution ~~{"ApprovalVotingMessage"}~~>  *
cycle(003) ∈ γ: CandidateBacking ~~{"CollatorProtocolMessage"}~~> CollatorProtocol ~~{"CandidateBackingMessage"}~~>  *
cycle(004) ∈ δ: NetworkBridgeRx ~~{"GossipSupportMessage"}~~> GossipSupport ~~{"NetworkBridgeRxMessage"}~~>  *
   Compiling frame-storage-access-test-runtime v0.4.0
   Compiling depow-runtime v0.1.0 (/home/ubuntu/DePow/blockchain/runtime)
   Compiling frame-benchmarking-cli v51.0.0
   Compiling polkadot-service v28.0.0
   Compiling cumulus-relay-chain-minimal-node v0.28.0
   Compiling polkadot-cli v28.0.1
warning: depow-runtime@0.1.0: You are building WASM runtime using `wasm32-unknown-unknown` target, although Rust >= 1.84 supports `wasm32v1-none` target!
warning: depow-runtime@0.1.0: You can install it with `rustup target add wasm32v1-none --toolchain stable-x86_64-unknown-linux-gnu` if you're using `rustup`.
warning: depow-runtime@0.1.0: After installing `wasm32v1-none` target, you must rebuild WASM runtime from scratch, use `cargo clean` before building.
   Compiling cumulus-relay-chain-inprocess-interface v0.28.0
   Compiling cumulus-client-service v0.28.0
   Compiling polkadot-omni-node-lib v0.10.0
   Compiling polkadot-sdk v2509.0.0
   Compiling depow-primitives v0.1.0 (/home/ubuntu/DePow/blockchain/primitives)
   Compiling pallet-fee-delegation v0.1.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-fee-delegation)
   Compiling pallet-social-recovery v1.0.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-social-recovery)
warning: unused import: `polkadot_sdk::frame_support::pallet_prelude`
 --> primitives/src/auctions.rs:5:5
  |
5 | use polkadot_sdk::frame_support::pallet_prelude::*;
  |     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  |
  = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: unused import: `polkadot_sdk::frame_support::pallet_prelude`
 --> primitives/src/types/status.rs:3:5
  |
3 | use polkadot_sdk::frame_support::pallet_prelude::*;
  |     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused import: `polkadot_sdk::frame_support::pallet_prelude`
 --> primitives/src/types/financial.rs:3:5
  |
3 | use polkadot_sdk::frame_support::pallet_prelude::*;
  |     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   Compiling pallet-energy-distribution-nft v1.0.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-energy-distribution-nft)
   Compiling pallet-depow-nft v0.1.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-depow-nft)
   Compiling pallet-oracle-integration v0.1.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-oracle-integration)
   Compiling pallet-liquidation-defi v0.1.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-liquidation-defi)
   Compiling pallet-marketplace v0.1.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-marketplace)
   Compiling pallet-meter-management v0.2.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-meter-management)
warning: `depow-primitives` (lib) generated 3 warnings
   Compiling pallet-governance v0.1.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-governance)
warning: use of deprecated constant `pallet::warnings::ConstantWeight_0::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
  --> pallets/pallet-governance/src/lib.rs:50:26
   |
50 |         #[pallet::weight(10_000)]
   |                          ^^^^^^
   |
   = note: `#[warn(deprecated)]` on by default

warning: use of deprecated constant `pallet::RuntimeEvent::_w`: 
                 It is deprecated to have `RuntimeEvent` associated type in the pallet config.
                 Please instead remove it as it is redundant since associated bound gets appended automatically: 
                 
                 pub trait Config: frame_system::Config<RuntimeEvent: From<Event<Self>>> { }.
         
                 For more info see:
                     <https://github.com/paritytech/polkadot-sdk/pull/7229>
   --> pallets/pallet-oracle-integration/src/lib.rs:116:14
    |
116 |         type RuntimeEvent: From<Event<Self>> + IsType<<Self as polkadot_sdk::frame_system::Config>::RuntimeEvent>;
    |              ^^^^^^^^^^^^
    |
    = note: `#[warn(deprecated)]` on by default

warning: unused import: `MaxEncodedLen`
  --> pallets/pallet-liquidation-defi/src/lib.rs:40:29
   |
40 | use codec::{Encode, Decode, MaxEncodedLen};
   |                             ^^^^^^^^^^^^^
   |
   = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: use of deprecated constant `pallet::RuntimeEvent::_w`: 
                 It is deprecated to have `RuntimeEvent` associated type in the pallet config.
                 Please instead remove it as it is redundant since associated bound gets appended automatically: 
                 
                 pub trait Config: frame_system::Config<RuntimeEvent: From<Event<Self>>> { }.
         
                 For more info see:
                     <https://github.com/paritytech/polkadot-sdk/pull/7229>
  --> pallets/pallet-liquidation-defi/src/lib.rs:58:14
   |
58 |         type RuntimeEvent: From<Event<Self>> + IsType<<Self as polkadot_sdk::frame_system::Config>::RuntimeEvent>;
   |              ^^^^^^^^^^^^
   |
   = note: `#[warn(deprecated)]` on by default

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_0::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:332:16
    |
332 |         pub fn liquidate_expired_energy(
    |                ^^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_1::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:364:16
    |
364 |         pub fn convert_to_dcop(
    |                ^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_2::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:392:16
    |
392 |         pub fn process_liquidation_queue(
    |                ^^^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_3::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:419:16
    |
419 |         pub fn create_liquidation_auction(
    |                ^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_4::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:463:16
    |
463 |         pub fn place_liquidation_bid(
    |                ^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_5::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:505:16
    |
505 |         pub fn finalize_liquidation_auction(
    |                ^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_6::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:547:16
    |
547 |         pub fn cancel_liquidation_auction(
    |                ^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_7::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:567:16
    |
567 |         pub fn record_debt(
    |                ^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_8::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:626:16
    |
626 |         pub fn update_debt_status(
    |                ^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_9::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:658:16
    |
658 |         pub fn process_payment(
    |                ^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_10::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:704:16
    |
704 |         pub fn settle_debt(
    |                ^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_11::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:748:16
    |
748 |         pub fn liquidate_collateral(
    |                ^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_12::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:798:16
    |
798 |         pub fn update_liquidation_rate(
    |                ^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_13::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:813:16
    |
813 |         pub fn update_liquidation_fee(
    |                ^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_14::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:828:16
    |
828 |         pub fn pause_pallet(origin: OriginFor<T>) -> DispatchResult {
    |                ^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_15::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:837:16
    |
837 |         pub fn unpause_pallet(origin: OriginFor<T>) -> DispatchResult {
    |                ^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_16::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:846:16
    |
846 |         pub fn sync_oracle_rates(origin: OriginFor<T>) -> DispatchResult {
    |                ^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ImplicitCallIndex_17::_w`: 
                 It is deprecated to use implicit call indices.
                 Please instead ensure that all calls have a `pallet::call_index` attribute or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/12891>
                     <https://github.com/paritytech/substrate/pull/11381>
   --> pallets/pallet-liquidation-defi/src/lib.rs:857:16
    |
857 |         pub fn batch_liquidate_dynamic(
    |                ^^^^^^^^^^^^^^^^^^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_0::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:331:26
    |
331 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_1::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:363:26
    |
363 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_2::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:391:26
    |
391 |         #[pallet::weight(50_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_3::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:418:26
    |
418 |         #[pallet::weight(20_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_4::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:462:26
    |
462 |         #[pallet::weight(15_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_5::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:504:26
    |
504 |         #[pallet::weight(20_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_6::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:546:26
    |
546 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_7::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:566:26
    |
566 |         #[pallet::weight(15_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_8::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:625:26
    |
625 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_9::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:657:26
    |
657 |         #[pallet::weight(15_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_10::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:703:26
    |
703 |         #[pallet::weight(20_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_11::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:747:26
    |
747 |         #[pallet::weight(25_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_12::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:797:26
    |
797 |         #[pallet::weight(5_000)]
    |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_13::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:812:26
    |
812 |         #[pallet::weight(5_000)]
    |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_14::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:827:26
    |
827 |         #[pallet::weight(5_000)]
    |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_15::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:836:26
    |
836 |         #[pallet::weight(5_000)]
    |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_16::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:845:26
    |
845 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_17::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-liquidation-defi/src/lib.rs:856:26
    |
856 |         #[pallet::weight(50_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_0::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1063:26
     |
1063 |         #[pallet::weight(50_000)]
     |                          ^^^^^^
     |
     = note: `#[warn(deprecated)]` on by default

warning: use of deprecated constant `pallet::warnings::ConstantWeight_1::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1129:26
     |
1129 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_2::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1143:26
     |
1143 |         #[pallet::weight(30_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_3::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1198:26
     |
1198 |         #[pallet::weight(20_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_4::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1252:26
     |
1252 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_5::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1296:26
     |
1296 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_6::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1330:26
     |
1330 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_7::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1402:26
     |
1402 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_8::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1449:26
     |
1449 |         #[pallet::weight(15_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_9::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1498:26
     |
1498 |         #[pallet::weight(5_000)]
     |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_10::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1532:26
     |
1532 |         #[pallet::weight(5_000)]
     |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_11::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1549:26
     |
1549 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_12::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1628:26
     |
1628 |         #[pallet::weight(5_000)]
     |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_13::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1659:26
     |
1659 |         #[pallet::weight(5_000)]
     |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_14::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1677:26
     |
1677 |         #[pallet::weight(5_000)]
     |                          ^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_15::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1699:26
     |
1699 |         #[pallet::weight(50_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_16::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1728:26
     |
1728 |         #[pallet::weight(50_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_17::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1779:26
     |
1779 |         #[pallet::weight(50_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_18::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1832:26
     |
1832 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_19::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1867:26
     |
1867 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_20::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1897:26
     |
1897 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_21::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1932:26
     |
1932 |         #[pallet::weight(10_000)]
     |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_22::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:1969:26
     |
1969 |         #[pallet::weight(50_000)]
     |                          ^^^^^^

warning: unused import: `Saturating`
 --> pallets/pallet-oracle-integration/src/mock_iot.rs:5:40
  |
5 | use polkadot_sdk::sp_runtime::traits::{Saturating, UniqueSaturatedInto};
  |                                        ^^^^^^^^^^
  |
  = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: unused import: `sp_runtime::traits::UniqueSaturatedInto`
  --> pallets/pallet-oracle-integration/src/lib.rs:25:5
   |
25 |     sp_runtime::traits::UniqueSaturatedInto,
   |     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: associated functions `generate_mock_price` and `calculate_mock_energy` are never used
   --> pallets/pallet-oracle-integration/src/lib.rs:461:8
    |
446 | impl<T: Config> Pallet<T> {
    | ------------------------- associated functions in this implementation
...
461 |     fn generate_mock_price() -> u128 {
    |        ^^^^^^^^^^^^^^^^^^^
...
477 |     fn calculate_mock_energy(hour: u64, panel_id: u64) -> u64 {
    |        ^^^^^^^^^^^^^^^^^^^^^
    |
    = note: `#[warn(dead_code)]` (part of `#[warn(unused)]`) on by default

warning: unused variable: `reason`
   --> pallets/pallet-marketplace/src/lib.rs:978:13
    |
978 |             reason: BoundedVec<u8, ConstU32<256>>,
    |             ^^^^^^ help: if this is intentional, prefix it with an underscore: `_reason`
    |
    = note: `#[warn(unused_variables)]` (part of `#[warn(unused)]`) on by default

warning: unused variable: `now`
    --> pallets/pallet-marketplace/src/lib.rs:1207:35
     |
1207 |         fn process_expired_orders(now: BlockNumberFor<T>) {
     |                                   ^^^ help: if this is intentional, prefix it with an underscore: `_now`

warning: unused variable: `now`
    --> pallets/pallet-marketplace/src/lib.rs:1212:36
     |
1212 |         fn process_ending_auctions(now: BlockNumberFor<T>) {
     |                                    ^^^ help: if this is intentional, prefix it with an underscore: `_now`

warning: `pallet-governance` (lib) generated 1 warning
warning: unused implementer of `polkadot_sdk::frame_support::traits::Imbalance` that must be used
   --> pallets/pallet-liquidation-defi/src/lib.rs:348:13
    |
348 |             T::Currency::deposit_creating(&who, final_amount);
    |             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |
    = note: `#[warn(unused_must_use)]` (part of `#[warn(unused)]`) on by default

warning: unused implementer of `polkadot_sdk::frame_support::traits::Imbalance` that must be used
   --> pallets/pallet-liquidation-defi/src/lib.rs:384:13
    |
384 |             T::Currency::deposit_creating(&who, final_amount);
    |             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused implementer of `polkadot_sdk::frame_support::traits::Imbalance` that must be used
   --> pallets/pallet-liquidation-defi/src/lib.rs:407:21
    |
407 |                     T::Currency::deposit_creating(&account, dcop_amount);
    |                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused implementer of `polkadot_sdk::frame_support::traits::Imbalance` that must be used
   --> pallets/pallet-liquidation-defi/src/lib.rs:904:21
    |
904 |                     T::Currency::deposit_creating(account, dcop_amount);
    |                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused variable: `block`
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:2434:27
     |
2434 |         fn block_to_month(block: BlockNumberFor<T>) -> u32 {
     |                           ^^^^^ help: if this is intentional, prefix it with an underscore: `_block`
     |
     = note: `#[warn(unused_variables)]` (part of `#[warn(unused)]`) on by default

warning: `pallet-oracle-integration` (lib) generated 4 warnings
warning: `pallet-marketplace` (lib) generated 3 warnings
warning: `pallet-liquidation-defi` (lib) generated 42 warnings (run `cargo fix --lib -p pallet-liquidation-defi` to apply 1 suggestion)
   Compiling pallet-solar-farm-management v1.0.0 (/home/ubuntu/DePow/blockchain/pallets/pallet-solar-farm-management)
warning: `pallet-energy-distribution-nft` (lib) generated 24 warnings
warning: use of deprecated constant `pallet::warnings::ConstantWeight_0::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:280:26
    |
280 |         #[pallet::weight(10_000)]
    |                          ^^^^^^
    |
    = note: `#[warn(deprecated)]` on by default

warning: use of deprecated constant `pallet::warnings::ConstantWeight_1::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:378:26
    |
378 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_2::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:417:26
    |
417 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_3::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:467:26
    |
467 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_4::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:526:26
    |
526 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_5::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:561:26
    |
561 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_6::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:602:26
    |
602 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: use of deprecated constant `pallet::warnings::ConstantWeight_7::_w`: 
                 It is deprecated to use hard-coded constant as call weight.
                 Please instead benchmark all calls or put the pallet into `dev` mode.
         
                 For more info see:
                     <https://github.com/paritytech/substrate/pull/13798>
   --> pallets/pallet-solar-farm-management/src/lib.rs:678:26
    |
678 |         #[pallet::weight(10_000)]
    |                          ^^^^^^

warning: `pallet-solar-farm-management` (lib) generated 8 warnings
warning: unused doc comment
   --> runtime/src/lib.rs:370:1
    |
370 | / /// Asset ID constants for DePow tokens
371 | | ///
372 | | /// Architecture:
373 | | /// - AssetId 1 = DCOP (Stablecoin, comes from external service/parachain, NOT minted here)
374 | | /// - AssetId 2 = DCO2 (Carbon Credits, minted when ETD is minted, ratio varies by farm type)
375 | | /// - AssetId 3 = ETD (Energy Token, minted when Oracle_IoT_Co reports meter readings, 1 ETD = 1 kWh)
    | |_----------------------------------------------------------------------------------------------------^
    |   |
    |   rustdoc does not generate documentation for macro invocations
    |
    = help: to document an item produced by a macro, the macro must produce the documentation as part of its expansion
    = note: `#[warn(unused_doc_comments)]` (part of `#[warn(unused)]`) on by default

warning: use of deprecated struct `polkadot_sdk::pallet_transaction_payment::CurrencyAdapter`: Please use the fungible trait and FungibleAdapter. This struct will be removed some time after March 2024.
  --> runtime/src/lib.rs:65:54
   |
65 |     pallet_transaction_payment::{ConstFeeMultiplier, CurrencyAdapter, Multiplier},
   |                                                      ^^^^^^^^^^^^^^^
   |
   = note: `#[warn(deprecated)]` on by default

warning: `depow-runtime` (lib) generated 2 warnings
   Compiling depow-node v0.1.0 (/home/ubuntu/DePow/blockchain/node)
warning: unused import: `self as json`
  --> node/src/chain_spec.rs:18:18
   |
18 | use serde_json::{self as json};
   |                  ^^^^^^^^^^^^
   |
   = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: unused import: `codec::Encode`
  --> node/src/service.rs:12:5
   |
12 | use codec::Encode;
   |     ^^^^^^^^^^^^^

warning: unused import: `BlakeTwo256`
  --> pallets/pallet-oracle-integration/src/mock.rs:11:18
   |
11 |         traits::{BlakeTwo256, IdentityLookup},
   |                  ^^^^^^^^^^^
   |
   = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: unused import: `BlakeTwo256`
  --> pallets/pallet-marketplace/src/mock.rs:13:18
   |
13 |         traits::{BlakeTwo256, IdentityLookup},
   |                  ^^^^^^^^^^^
   |
   = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: unused import: `frame_system::Call as SystemCall`
   --> pallets/pallet-marketplace/src/mock.rs:135:9
    |
135 | pub use frame_system::Call as SystemCall;
    |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused import: `pallet_balances::Call as BalancesCall`
   --> pallets/pallet-marketplace/src/mock.rs:136:9
    |
136 | pub use pallet_balances::Call as BalancesCall;
    |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused import: `polkadot_sdk::sp_core::H256`
   --> pallets/pallet-marketplace/src/mock.rs:139:9
    |
139 | pub use polkadot_sdk::sp_core::H256;
    |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused import: `Event`
 --> pallets/pallet-marketplace/src/tests.rs:6:29
  |
6 | use crate::{mock::*, Error, Event, OrderType, AssetType};
  |                             ^^^^^

warning: unused imports: `BlakeTwo256` and `traits::Everything`
  --> pallets/pallet-depow-nft/src/mock.rs:7:9
   |
 7 |         traits::Everything,
   |         ^^^^^^^^^^^^^^^^^^
...
14 |         traits::{BlakeTwo256, IdentityLookup},
   |                  ^^^^^^^^^^^
   |
   = note: `#[warn(unused_imports)]` (part of `#[warn(unused)]`) on by default

warning: unused import: `frame_system::Call as SystemCall`
   --> pallets/pallet-depow-nft/src/mock.rs:170:9
    |
170 | pub use frame_system::Call as SystemCall;
    |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unused import: `pallet_balances::Call as BalancesCall`
   --> pallets/pallet-depow-nft/src/mock.rs:171:9
    |
171 | pub use pallet_balances::Call as BalancesCall;
    |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: unexpected `cfg` condition value: `deprecated-tests`
   --> pallets/pallet-depow-nft/src/tests.rs:159:7
    |
159 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: link_panel_to_meter functionality removed
    |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |
    = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
    = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
    = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration
    = note: `#[warn(unexpected_cfgs)]` on by default

warning: unexpected `cfg` condition value: `deprecated-tests`
   --> pallets/pallet-depow-nft/src/tests.rs:195:7
    |
195 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: link_panel_to_meter functionality removed
    |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |
    = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
    = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
    = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
   --> pallets/pallet-depow-nft/src/tests.rs:905:7
    |
905 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: link_panel_to_meter functionality removed
    |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |
    = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
    = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
    = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
   --> pallets/pallet-depow-nft/src/tests.rs:971:7
    |
971 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: link_panel_to_meter and unlink_panel_from_meter functionality ...
    |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |
    = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
    = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
    = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
    --> pallets/pallet-depow-nft/src/tests.rs:1027:7
     |
1027 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: PanelLinkedCannotSell error and can_sell field removed
     |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     |
     = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
     = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
     = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
    --> pallets/pallet-depow-nft/src/tests.rs:1095:7
     |
1095 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: transfer_meter_with_panels function and linked_panels field r...
     |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     |
     = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
     = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
     = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
    --> pallets/pallet-depow-nft/src/tests.rs:1174:7
     |
1174 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: transfer_meter_with_panels function removed
     |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     |
     = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
     = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
     = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
    --> pallets/pallet-depow-nft/src/tests.rs:1211:7
     |
1211 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: unlink_panel_from_meter function and related fields removed
     |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     |
     = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
     = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
     = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
    --> pallets/pallet-depow-nft/src/tests.rs:1270:7
     |
1270 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: unlink_panel_from_meter function removed
     |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     |
     = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
     = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
     = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unexpected `cfg` condition value: `deprecated-tests`
    --> pallets/pallet-depow-nft/src/tests.rs:1295:7
     |
1295 | #[cfg(feature = "deprecated-tests")] // DEPRECATED: transfer_meter_with_panels function removed
     |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
     |
     = note: expected values for `feature` are: `default`, `runtime-benchmarks`, `std`, and `try-runtime`
     = help: consider adding `deprecated-tests` as a feature in `Cargo.toml`
     = note: see <https://doc.rust-lang.org/nightly/rustc/check-cfg/cargo-specifics.html> for more information about checking conditional configuration

warning: unused import: `Saturating`
 --> pallets/pallet-oracle-integration/src/mock_iot.rs:5:40
  |
5 | use polkadot_sdk::sp_runtime::traits::{Saturating, UniqueSaturatedInto};
  |                                        ^^^^^^^^^^

warning: function `clear_mock_nft_data` is never used
  --> pallets/pallet-oracle-integration/src/mock.rs:69:8
   |
69 | pub fn clear_mock_nft_data() {
   |        ^^^^^^^^^^^^^^^^^^^

warning: type alias `Balance` is never used
   --> pallets/pallet-marketplace/src/mock.rs:141:10
    |
141 | pub type Balance = <Test as pallet_balances::Config>::Balance;
    |          ^^^^^^^
    |
    = note: `#[warn(dead_code)]` (part of `#[warn(unused)]`) on by default

warning: constant `DAVE` is never used
   --> pallets/pallet-marketplace/src/mock.rs:147:11
    |
147 | pub const DAVE: AccountId = 4;
    |           ^^^^

warning: constant `EVE` is never used
   --> pallets/pallet-marketplace/src/mock.rs:148:11
    |
148 | pub const EVE: AccountId = 5;
    |           ^^^

warning: type alias `Balance` is never used
   --> pallets/pallet-depow-nft/src/mock.rs:175:10
    |
175 | pub type Balance = <Test as pallet_balances::Config>::Balance;
    |          ^^^^^^^
    |
    = note: `#[warn(dead_code)]` (part of `#[warn(unused)]`) on by default

warning: constant `EVE` is never used
   --> pallets/pallet-depow-nft/src/mock.rs:182:11
    |
182 | pub const EVE: AccountId = 5;
    |           ^^^

warning: unused variable: `farm_id`
    --> pallets/pallet-energy-distribution-nft/src/tests.rs:1013:13
     |
1013 |         let farm_id = 1u32;
     |             ^^^^^^^
     |
     = note: `#[warn(unused_variables)]` (part of `#[warn(unused)]`) on by default
help: if this is intentional, prefix it with an underscore
     |
1013 |         let _farm_id = 1u32;
     |             +
help: you might have meant to pattern match on the similarly named constant `DCO2_RATIO_PRECISION`
     |
1013 -         let farm_id = 1u32;
1013 +         let pallet::DCO2_RATIO_PRECISION = 1u32;
     |

warning: unused variable: `solar_farm_owner`
    --> pallets/pallet-energy-distribution-nft/src/tests.rs:1276:13
     |
1276 |         let solar_farm_owner = 10u64;
     |             ^^^^^^^^^^^^^^^^ help: if this is intentional, prefix it with an underscore: `_solar_farm_owner`

warning: unused variable: `block`
    --> pallets/pallet-energy-distribution-nft/src/lib.rs:2434:27
     |
2434 |         fn block_to_month(block: BlockNumberFor<T>) -> u32 {
     |                           ^^^^^ help: if this is intentional, prefix it with an underscore: `_block`

error: linking with `cc` failed: exit status: 1
  |
  = note:  "cc" "-m64" "/tmp/rustcr8cBgr/symbols.o" "<118 object files omitted>" "-Wl,--as-needed" "-Wl,-Bstatic" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib/{libtest-*,libgetopts-*}.rlib" "/home/ubuntu/DePow/blockchain/target/debug/deps/{libpolkadot_sdk-98af269c44f60536,libsubstrate_wasm_builder-16088889cc02d34d,libjobserver-ebb3010277890062,libpolkavm_linker-b8b75b8be7119dbf,libdirs-0e6f1e42452572e3,libregalloc2-029b251ef8be94d0,libslice_group_by-f1fedd16c3ecbe49,libshlex-834e721b3c6c6a50,libfiletime-896c40975e64fdcd,libwasm_opt-785acc795f747f0a,libwasm_opt_cxx_sys-16bad0093342946f,libwasm_opt_sys-e082691d989a5c45,libcxx-49d8e88983791154,liblink_cplusplus-87df92ec8539cf6c,libwalkdir-5b17f7d93ab63aa9,libsame_file-7c8ad0c8c9fe0e05,libcargo_metadata-0d632bd30baecabf,libcargo_platform-b4dbe4809d079bb6,libcamino-0996bd698384ad86,libbuild_helper-3d072b35b20c2265,libsemver-81b661d38b005dcc,libsemver_parser-384304630514f989,libsubstrate_frame_rpc_support-9e5e2c5577ff7e67,libsubstrate_build_script_utils-f686463c69dc9652,libsubkey-7fbf5699bfa3d5f0,libstaging_node_inspect-789c81c5a5eec8d8,libsp_core_hashing_proc_macro-32d538f9b5e47ef1,libsp_core_hashing-b0ac283bad93aa23,libsc_consensus_pow-febd2a9710048995,libsp_consensus_pow-7e6f4b9fd4240ec8,libpolkadot_omni_node_lib-69b661f197829b76,libsc_network_statement-d0476080db9d3519,libcolor_print-ea403151c8715551,libsc_consensus_manual_seal-9cf79bcc3b28f961,libsc_statement_store-c85dcfd12cfce35d,libstaging_chain_spec_builder-c27c639c3260601e,libpolkadot_node_core_pvf_prepare_worker-4c4e72b042223d7e,libtikv_jemallocator-b7e42bf674ad792c,libstaging_tracking_allocator-09b1a751b79e5c3c,libpolkadot_node_core_pvf_execute_worker-333c54e87f5ad065,libpallet_sudo-9186b5652d61c6dd,libpallet_revive_eth_rpc-e45239df35a80e88,libsqlx-5d9c45ad59dbcd27,libsqlx_sqlite-81d89086e7279aee,libflume-3255ce2f0fc3840a,libserde_urlencoded-a64231c7275741f4,libfutures_intrusive-b3e1b3b0f73113fa,liblibsqlite3_sys-1f63f857be5dd60e,libatoi-34e39a99c154b103,libsqlx_core-ddc9688a229a6ff8,libhashlink-95661769fc82641e,libevent_listener-e2058512768cf4b1,libparking-d405a45bca78b675,libpallet_grandpa-c36cc11290577245,libpallet_contracts_mock_network-fbb8d4410e15508e,libpallet_contracts-1cc59ba504fb4b44,libwasmi-cb3ae6cb6ab2416a,libwasmi_collections-fe627ab73aad72ea,libstring_interner-6e92f9b99c85da39,libwasmi_core-b05b5862410a3ce0,libdowncast_rs-dfebbdb571f15c7f,libmulti_stash-0db997889556dc50,libwasmparser_nostd-b5000577541c8e84,libindexmap_nostd-3a0f12419eae3e20,libpallet_contracts_uapi-40ecd485ca1e0e50,libgenerate_bags-7ad4e5faadad3529,libframe_support_procedural_tools-ff2076ae082fbfb8,libsyn-61f3ab5d0e145bad,libquote-c00c74433ac9180f,libproc_macro2-46bda76951fa7f45,libunicode_ident-4c7da432017fce16}.rlib" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib/{libproc_macro-*,librustc_literal_escaper-*,librustc_std_workspace_std-*}.rlib" "/home/ubuntu/DePow/blockchain/target/debug/deps/{libproc_macro_crate-b0663b644d326720,libtoml_edit-d8c84f73c7ab9548,libtoml_parser-9e387b9f140b2d65,libtoml_datetime-9a39996ce0166876,libframe_remote_externalities-1de8b1f3ee3c0cb1,libtokio_retry-495ce14893d5c930,libsubstrate_rpc_client-92012465c4821574,libindicatif-0b5074783497f601,libnumber_prefix-3a2388bf1d421940,libspinners-b893dafe6a248470,libmaplit-d4165f096a57f0d7,libstrum-f0942e02b4e67f71,libemulated_integration_tests_common-17bd8adee68ece16,libpallet_whitelist-328774b0d9872c6b,libpolkadot_sdk_frame-fb85564f29b39a95,libframe_executive-51f8184729044653,libxcm_emulator-cd0281db9ac4490a,libxcm_simulator-89192a15374a82b0,libcumulus_pallet_xcm-d8ef43c272674ae0,libcumulus_pallet_aura_ext-981be51cb0253e5e,libpallet_aura-ce5f337f48d101c5,libcumulus_client_service-418c5a832415cca1,libcumulus_relay_chain_minimal_node-cc1a5a147b7b1b4e,libcumulus_relay_chain_rpc_interface-9059354811fbf44f,libcumulus_relay_chain_inprocess_interface-34d2ca462a16d04a,libpolkadot_cli-da8ed7de1ba2b0a2,libsc_storage_monitor-fd3eeb0c43844f92,libfs4-cd1383d892e93f77,librustix-163a8bb80649f972,liblinux_raw_sys-be563daf86b20b65,libpolkadot_service-61fc825a2aeb9ba7,libpolkadot_node_core_parachains_inherent-a6fa0e152a838b68,libpolkadot_rpc-66b7fbfd7aa55ff7,libsubstrate_state_trie_migration_rpc-e0e05423e85f0419,libsubstrate_frame_rpc_system-7488008b3863f668,libsc_consensus_grandpa_rpc-7d5d6353e15810f4,libsc_consensus_beefy_rpc-19bce9fbc70ecec9,libsc_consensus_babe_rpc-fc3fd50a0fc307fb,libpallet_transaction_payment_rpc-b9806ff952d268ff,libmmr_rpc-2cd80e8f2ff8b49a,libsc_consensus_beefy-beb4e994fbd06fa3,libpallet_transaction_payment_rpc_runtime_api-349bb3fe67b2d425,libframe_system_rpc_runtime_api-b1215306f3078194,libsc_sync_state_rpc-3c0cf4d83197817f,libis_executable-e08b7fa8a191c193,libpolkadot_statement_distribution-98fdb07449ee4ec9,libpolkadot_node_core_runtime_api-1c6f279718000bf8,libpolkadot_node_core_pvf_checker-dda1c4d28a71f788,libpolkadot_node_core_provisioner-a0e01f61d705f993,libpolkadot_node_core_prospective_parachains-85e95504b1ac122f,libpolkadot_node_core_chain_api-be84a94b7a403232,libpolkadot_node_core_bitfield_signing-90d9ab170b1e5c65,libpolkadot_node_core_backing-5ed288856b2c2ff4,libpolkadot_node_core_approval_voting_parallel-ffe55b7ea44ac1f5,libpolkadot_node_collation_generation-6e7a38c6299ffec9,libpolkadot_gossip_support-921b59396cc4bcbd,libpolkadot_dispute_distribution-39cd25c6192f6d52,libpolkadot_collator_protocol-1f0a4fcbaed1f745,libpolkadot_availability_bitfield_distribution-812cd9a5b8a35fb8,libpolkadot_approval_distribution-921f03457541cf46,libpolkadot_availability_distribution-8accfe39fc718f46,libpolkadot_network_bridge-e6a325b5d5253f54,libpolkadot_node_core_dispute_coordinator-c18a6050247a871c,libpolkadot_node_core_chain_selection-f55b380b4a6dc5b4,libpolkadot_node_core_candidate_validation-b33c04e7f13f4dda,libpolkadot_node_core_pvf-164fb5d81c89bf79,libslotmap-23c04bee080bb582,libpolkadot_node_core_pvf_common-814c1c3ce1b4104d,libcpu_time-62711d61d82ab9ba,libseccompiler-b10c1acf0b4d40f3,liblandlock-619169d40c41817a,libnix-ea97d5e373196ce2,libalways_assert-b83f0309eed23856,libpolkadot_node_core_av_store-2fb9a1ac01225d8d,libpolkadot_availability_recovery-75bd05d119606447,libmmr_gadget-2252a559c5d85a84,libsc_offchain-3c839c236038bd36,libthreadpool-adb90ecfa55f5451,libframe_benchmarking_cli-2d83311f0462b6a0,libgethostname-702259f180fd9a2c,libenv_filter-eb8263edf07d0cab,libframe_storage_access_test_runtime-402418997db413b8,libinflector-685fcef610d0a6c4,libframe_benchmarking-f07c9ea701b7f713,liblinregress-87ae813550f5912e,libnalgebra-7257b88717810b69,libmatrixmultiply-7214ec51e047fb13,librawpointer-71563accd9c427ed,libsimba-7f6da60a798555b6,libwide-1ef7bb7d6579ffe8,libsafe_arch-538a7c9cf339dc81,libbytemuck-1b4bef5f338586fe,libnum_complex-5fc1f5b52802fbc1,libhandlebars-75085d734e04d7b2,libpest-0be0fc4f5936db64,libucd_trie-76c2a9515b97695d,libsubxt-9fc67705e514dc32,libsubxt_rpcs-5746c27eb094d306,libfinito-b3821ac3f44899e6,libsc_runtime_utilities-8fff403d49a27912,libcomfy_table-049bb46cc8ce6ccb,libunicode_segmentation-1ff1aec11bbc1d36,libthousands-6cda707d9bd896cc,libsc_consensus_grandpa-b768f91c3b13a9bc,libsc_network_gossip-eaa8b8c8a39b5198,libpolkadot_node_core_approval_voting-10f3c3f4ea776615,libsp_consensus_beefy-a77786d788de19c0,libsp_mmr_primitives-bee41c6862433fae,libpolkadot_ckb_merkle_mountain_range-e6d5524f9f5dc8ef,libitertools-c537e75bd0786902,libcumulus_primitives_proof_size_hostfunction-5566d83fdb28f797,libcumulus_client_consensus_relay_chain-3095dfa5330a3992,libcumulus_client_consensus_aura-530d6eaa4f9f8777,libpolkadot_node_subsystem_util-f7bdfe54552bfe1a,libpolkadot_erasure_coding-044c57bef760b53d,libreed_solomon_novelpoly-8c473a9717f440f5,libcumulus_primitives_aura-d0cef32a609c53f9,libcumulus_client_parachain_inherent-8fa97278fc2f8ad4,libcumulus_client_consensus_proposer-b1a8f81132ba57cb,libsc_basic_authorship-35aa3df91ba74b3c,libsc_proposer_metrics-3e0d5ea48f60cd9d,libsc_block_builder-c5fadfb8642fdaa0,libsc_consensus_aura-3fa123208fe4fa18,libcumulus_client_collator-c3d3a1c872147e53,libcumulus_client_network-0ad9b563c89bad50,libcumulus_client_consensus_common-2bb1fa0e75945806,libsc_consensus_babe-f693f882b6a5250b,libnum_rational-b7d8474f5da7b7d9,libsp_block_builder-f591ec64fa34b937,libsc_consensus_slots-be0e5a480a150667,libsc_consensus_epochs-60921b692815857a,libcumulus_client_pov_recovery-ccff7272ed8d61d4,libcumulus_relay_chain_streams-1397c3f93ecb2f58,libpolkadot_node_subsystem-3869ca286ffd27be,libcumulus_client_cli-ade69bac3091d9e0,libcumulus_client_bootnodes-acfa282c2521ef84,libcumulus_relay_chain_interface-8c7923def20f915f,libpolkadot_overseer-8e8723f4aed1bf7b,libtikv_jemalloc_ctl-77ff53f658103548,libtikv_jemalloc_sys-169974383fe1c222,libpolkadot_node_metrics-a4447f387d26c299,libsc_cli-617881c31f29d237,libfdlimit-e70d78aa6f4c71ea,librpassword-00600b3175db9e86,librtoolbox-b1acac122af90b81,libnames-11f1a9dc1501bbb9,libsc_service-e810b3a86f0f3a62,libsc_informant-2b32bd8df532a312,libsc_sysinfo-949604758bdefb0d,librand_pcg-754e2bf71d3675d6,libdirectories-0aa2f37ed02990ab,libdirs_sys-8a734b1cd4a4c53d,liboption_ext-791e6f42d0cc761e,libsp_transaction_storage_proof-7278b3a1d3f342b4,libstatic_init-cbe230b1a1a5eec2,libsc_network_transactions-4817b6a069a39930,libtracing_futures-57d7588899a791d2,libexit_future-fc8c32d741be3cb3,libsc_rpc_spec_v2-65f1403d29123abb,libsc_rpc-6770a63a55d4b037,libsp_offchain-f186f7e08dcf2501,libsc_tracing-bbe454957753471b,libis_terminal-832a0720c3701fea,libconsole-1e0cd8456b43f6da,libunicode_width-8521d0cba76a6144,libsp_statement_store-b11513be5d325b27,libaes_gcm-c8f99c1e3f9a79a8,libctr-68cb21b63042627d,libghash-db7edf2853dfd74d,libpolyval-392bd8192ba33e10,libopaque_debug-a4f012e41a473180,libuniversal_hash-6b9fbc17cad60fbd,libaes-b936a78899d86313,libcipher-e733a6dd82daeca7,libinout-3ad92d7440341fc4,libaead-d01a477925d8fce4,libsc_network_sync-7fe062ec1c490a61,libfork_tree-a6f5d40d479017f1,libsc_network_light-583f724e6337360d,libtempfile-a12820c6739866a6,libfastrand-4ca17b4d923f7d09,libsc_transaction_pool-8bbd8d5abd286c65,libsp_transaction_pool-71dbc7ab2612ead5,libsc_rpc_server-73666c5c16e8669b,libtower_http-8442a1a238c4a1fd,libsc_rpc_api-7da24ea414f9e90e,libsc_mixnet-ead843129b104948,libsp_mixnet-80ceb5f8d4bdb45a,libmixnet-0faf042c634abece,librand_distr-12b97f6a43231466,liblioness-914fa04ce2b4a83d,libblake2-713922ab3b4b6961,libcrypto_mac-fe93a091a3790567,libsubtle-4f8cf0f70c840721,libbyte_tools-e09074427588670e,libdigest-70216a37bd0ad07a,libgeneric_array-1ddc6e133bbadb35,libopaque_debug-c052b5c53791eb7b,libchacha-0faa30e49d1eecb1,libkeystream-6130d4eca8f38966,libc2_chacha-ed32c4795681230d,libcipher-19b758b714c1d8bf,libhashlink-6973fd2fdc936780,libsp_rpc-c7e51538f8a24a41,librustc_hash-3b79e8232350cf3a,libforwarded_header_value-a9ed985beaf120d6,libnonempty-9955b59286e94ad5,libgovernor-a4d03c068f4c2bb2,libquanta-0081e4108a7de9d1,libraw_cpuid-0bdec824ffd50b87,libdashmap-6560c1e0918d84fe,libnonzero_ext-d0b45501736186dc,libno_std_compat-e24ca93c350860e6,libsc_client_db-f938444ea3a8046d,libsysinfo-97b4f1294ec134d7,libparity_db-ae05db5e9ab5944c,libmemmap2-fcda6c9fe40329ab,libsnap-9898a1475d0500a7,liblz4-a5ae754b204ee8bd,liblz4_sys-a7f00bbdf772e355,libfs2-4161a679f17279f4,libsiphasher-98cfd176f882e3dc,libkvdb_memorydb-4dc310f0a97116c6,libsc_state_db-21b7427b89091bfd,libkvdb_rocksdb-640095fd38ee254d,librocksdb-ab4871e0ef253f9d,liblibrocksdb_sys-d1dd1e8c27ad77b2,libjsonrpsee-53f719d098aeff2b,libjsonrpsee_server-0478a9efd8180b5a,libroute_recognizer-57f8b40c07be09d2,libjsonrpsee_wasm_client-0b8a9c0cde1b850e,libjsonrpsee_ws_client-79bee8187cc46bd7,libjsonrpsee_client_transport-2730da86c9f54c41,libjsonrpsee_http_client-8f75788356e89d29,libhyper_rustls-130846b613af2374,librustls_platform_verifier-69fe32cedbb2f168,libtower-0d4102323bdec6db,libtower_layer-9ce6944a7b9fbe04,libjsonrpsee_core-63fedc73192e85fd,libjsonrpsee_types-4caca39546c18d53,libsc_chain_spec-c2c861426097edfa,libmemmap2-51c73a5ce8e39c3e,libclap-b56f5f05180050ed,libclap_builder-abe11c3255cb7cf0,libterminal_size-35c71ac979547937,libstrsim-08f9beca88bc3385,libanstream-9fd87b725ebcde9e,libanstyle_query-6aac056c348ee6b5,libis_terminal_polyfill-8eb15715dd1b4348,libcolorchoice-280757403274d424,libanstyle_parse-e92232a5ceecc849,libutf8parse-f8f3d52be9bca96f,libclap_lex-44a32cc27246fa49,libsc_telemetry-f5adcda9cd9c82be,libchrono-e9d2f620c7fd696a,libiana_time_zone-1812bd8a2108aee5,libsc_consensus-501a4a8f122c9317,libmockall-40d404cbff822eee,libpredicates_tree-d9609af0867c6f02,libtermtree-34073be187be5c13,libpredicates-9a10da274941e6ed,libanstyle-b0b8596b0b7b1c75,libpredicates_core-6a7b6ab0719e5ece,libfragile-f8121a397221fa3c,libdowncast-0af1872d6ada3e76,libpolkadot_node_subsystem_types-deecdefeda48ce3b,libpolkadot_statement_table-3507194da9c27038,libpolkadot_node_network_protocol-7fd88596e4b67508,libtracing_gum-ff1263935764acf5,libsc_authority_discovery-135df533c5e65e7e,libpolkadot_node_primitives-4e2db19203ccdc59,libsc_keystore-6205ed64d208bd63,libbounded_vec-6619b7c55b732bc9,libsc_network-68537f7200dd9992,libpartial_sort-6208e275ff793520,liblinked_hash_set-99cd858f315294ea,libwasm_timer-8aecfda2cf706b85,libip_network-0c35901f3c60366d,libsc_network_common-4b845f4408d2cf95,libsc_network_types-85ed5e3cf4fcbc46,libserde_with-3585f6812f200680,liblitep2p-819dd6acf195b293,libtokio_tungstenite-8281214384d0e8f8,librustls_native_certs-31e97ea40e75a57d,libopenssl_probe-9783bab9077d4fa4,libtokio_rustls-a4750db20bfb3101,libtungstenite-7a4a3a4c91003e41,libutf8-ae9b530d9f927b7a,libnetwork_interface-6324ad6d05e06297,libsimple_dns-ec9b1e4bbcadd2e5,libtokio_stream-9bab457febb12bd5,libcid-d0ea55ce112945ac,libprost-14e383d06ff889df,libmultiaddr-88a0f85a9253673f,libhickory_resolver-1c95d73c3b55d55c,libmoka-d3f79e0e3de0cda3,libtagptr-5e403d8a8e203790,libuuid-c21f09d12dada164,libcrossbeam_channel-dd0d55d496c6a2dd,libhickory_proto-f6f1b07bbcf0726a,libprost-67b52e821ee3894c,libcid-5fb3ee6bc1f46395,libmultihash-81825dc7509dd421,libblake2s_simd-853b74eb11486903,liblibp2p-077200c1091326c3,liblibp2p_yamux-0178e07852d92a88,libyamux-93420f44329ce5be,librand-f06af8018277d0e4,librand_chacha-d52e9d4a5654ff3c,librand_core-51a983d5e036e22b,libyamux-efc8946cfc3db037,liblibp2p_websocket-cf133fd184e01a91,libwebpki_roots-4a063c340e3691b3,libsoketto-aa527d60586841fb,libsha1-9b6e48af92b27617,libfutures_rustls-858d07dcd79ac854,librustls-b17913d19adb7e82,libwebpki-08ac281bc733918b,librustls_pki_types-e1b44771807811b1,liblibp2p_tcp-9601eb44ba42cfc5,liblibp2p_request_response-f566a57abae2683f,liblibp2p_ping-cf853c8210a51463,liblibp2p_noise-3ae9a795bd751f87,libx25519_dalek-15918086da2a5eee,libsnow-60b0c74d6f1f74b0,libring-7cddbc7071df080b,libuntrusted-8e652868e2848723,liblibp2p_mdns-a822113a6f0cc725,libif_watch-ffe3951da6cd637e,librtnetlink-a1e86ead4887a805,libnix-4ffd077e84a3bd8a,libnetlink_proto-0a28b5d3a902907f,libnetlink_sys-f7229f614fc0a3f7,libnetlink_packet_route-1e1629c15f26134f,libnetlink_packet_core-6177e9280b4d5a32,libnetlink_packet_utils-89d685a0ae829635,liblibp2p_kad-976441a58bfc8bf1,libuint-b9ff1d0af369505a,liblibp2p_identify-25f0f6a67693dbb9,libquick_protobuf_codec-3f724cc82898dc7b,libasynchronous_codec-d1a241bd8d427dd1,libfutures_bounded-b0eafce5414c01d6,liblibp2p_dns-204e19526bb0e920,libhickory_resolver-a70ef5bcdbab5705,libresolv_conf-778c371bdaadf6e7,liblru_cache-71e1a12f023870ba,liblinked_hash_map-1f38cde25ce3ffb8,libhickory_proto-c618635e9d4cb20a,libipnet-8e7cc3128782b543,libsocket2-b767b61e31f987da,liblibp2p_connection_limits-623a9c8e5064f86c,liblibp2p_allow_block_list-7f1347ae877ad395,liblibp2p_swarm-cd5a98353a0ac193,liblru-01cd6db15c1e9ab9,liblibp2p_core-650a1cdfa4e3c49e,libvoid-665039f8d4982a3d,libmultistream_select-a0b19df2e050d806,libunsigned_varint-c145f9534d0a7304,libasynchronous_codec-88be3c20880d7c3f,librw_stream_sink-284cff33ee71cd59,libweb_time-c24f3924985c7cb0,libmultiaddr-bc2c232bed946809,liburl-6157bb0125fe4e5d,libidna-3960f71eb1dcc62f,libutf8_iter-b6eaad6a6b2fc516,libidna_adapter-161525d08d8b5f75,libicu_properties-66e73f661faf16a9,libicu_properties_data-4c634182aa4f34d3,libicu_normalizer-f1dead93511c1be9,libicu_normalizer_data-9c4482b1e712a920,libicu_collections-bff15b1e2c8cb5e3,libpotential_utf-8b59145a4536cc14,libicu_provider-5668527c1f565249,libicu_locale_core-b9649ee7bab72786,libtinystr-503262d1a623f258,liblitemap-e161d9b2525d473e,libwriteable-a9b193e6be952911,libzerovec-757266703d2096fd,libzerotrie-0b4c45137bc32aac,libyoke-dcad382880fc8545,libzerofrom-feeb5e82b24346ef,libform_urlencoded-cfe4e7600c682b7a,libpercent_encoding-3d996758cd54bd6a,libmultibase-2f795cec8fd398e2,libbase_x-6d221b3416d255ab,libdata_encoding_macro-bfb8d7e513104098,liblibp2p_identity-c342d0ac6ee7a738,libhkdf-8701e69b969ad37f,libquick_protobuf-6a2650343cc1821c,libdata_encoding-18cc8d1e9d901793,libmultihash-725662b83cb1d4cf,libunsigned_varint-8db1f362a8452bf4,libfatality-57b1949a88d5dee0,liborchestra-664f537706f1fb74,libpin_project-51f5e5545bc5d33f,libdyn_clonable-8f2fc3b6a0354c2a,libprioritized_metered_channel-00364bcaee5bffd3,libcrossbeam_queue-691d966a2dbc5b91,libnanorand-1fd5b72fcf8af371,libcoarsetime-0c7bc23528a09b43,libsc_client_api-900226c217229a7e,libsc_utils-e808493d3e25603a,libfutures_timer-fae54f90ea4d8e58,libasync_channel-c293c6624a5dcb92,libevent_listener-b8603b37c20ef028,libconcurrent_queue-a378371ece4fa662,libsc_transaction_pool_api-8a89adca4f68f423,libsp_blockchain-f49c89b78f1f33b2,libsp_database-49f1773bdb64d41d,libkvdb-62a2dc0cf6e233c4,libsc_executor-aa9831b2d7435981,libsc_executor_polkavm-8f210805e8edf164,libsc_executor_wasmtime-460ea18065a6aa62,libsc_executor_common-6d5b32d5b5fdb8e1,libsc_allocator-0352e5cb7c5edf90,libsp_maybe_compressed_blob-6f823b4e70f2d7ad,libzstd-a7b8a9c1ba77eeb6,libzstd_safe-fc73518c36abae29,libwasm_instrument-079d8ab36d81084d,libpolkavm-ba501f283070021e,libpolkavm_common-964a8a509f84af4b,libpolkavm_assembler-6065c622e0569928,libsp_consensus-79bc853b60f79254,libbridge_hub_test_utils-ff1ff49baa3c8bea,libpallet_bridge_relayers-4359431d81fb2674,libbp_test_utils-b9235019f5fb5e5d,libpallet_xcm_bridge_hub-9f4a91706f04b686,libbp_xcm_bridge_hub-ac4d56459095d975,libpallet_bridge_parachains-e5a7e6f433ee33a9,libpallet_bridge_grandpa-869fbfaefd4b71d2,libsp_keyring-404ef77b08770e2b,libstrum-6c0270af34b95a10,libpallet_bridge_messages-e93020dfc742112b,libbp_relayers-df458f05d13ebcf7,libpallet_utility-2385b6c3bc417935,libbp_parachains-53be9c96dc9c788e,libbp_polkadot_core-4cbcfb9b6c6426a7,libbp_messages-8cf1365d3c930aaa,libbp_header_chain-ebd9db8dce8fd96a,libsp_consensus_grandpa-10ee968b325ceac9,libfinality_grandpa-3c216d60605c512f,libbp_runtime-41550dd63c18cec0,libasset_test_utils-e6433a05cf2fa6c8,libpallet_xcm_bridge_hub_router-43f09f4dda26c8e5,libbp_xcm_bridge_hub_router-fbbfb6c14c168faf,libparachains_runtimes_test_utils-c39676f9578b143a,libcumulus_pallet_xcmp_queue-5e3419615220d4c6,libapprox-53a002ee2eee6999,libcumulus_test_relay_sproof_builder-caddff293ae4efd1,libcumulus_pallet_parachain_system-cb3941f7e776df51,libcumulus_primitives_parachain_inherent-60ef439f90d48b81,libparachains_common-d81e5095bc9c25ee,libsp_consensus_aura-d966ced116189686,libstaging_parachain_info-e47702873c6abf92,libcumulus_primitives_utility-16d877c25defb228,libpallet_xcm-ae85c9b3e47e0830,libxcm_runtime_apis-94ccc079572852a8,libpallet_revive-fe26c525329e5f64,libsubxt_signer-d09ce48c035f0fcc,libbip32-1c1e8e9121cfe71f,libbip39-cbe6525dd6e3c83e,libsecp256k1-378632ccbbd1e7de,libsecp256k1_sys-ff6cb74119fa46c7,libsubxt_core-9e67c5ed68eb9a92,libkeccak_hash-76f767213f676c21,libscale_value-78dd67e1c01c7a75,libyap-8a248b835730274f,libbase58-88e3c929f414888c,libscale_encode-7c30901679167bf4,libsubxt_metadata-e4b8b48a867692a0,libhashbrown-1a3e82099a6bf33a,libframe_metadata-323ecdfad054d668,libframe_decode-ad0e9e5561f14a4f,libscale_decode-a4bb95774f94d0be,libscale_bits-eca687787275f89e,libframe_metadata-13fe43588b0484a5,libscale_type_resolver-4e96d99014db22c8,libsecrecy-8f7962d09cb48b6e,libhumantime_serde-fb79af18f3656551,libhumantime-8b27791cf870d0e2,libsubstrate_bn-cec7282c7f14427c,libethereum_types-85e3a9bb5f337349,libethbloom-ec0d9cfe0b6d7870,librevm-6da0fa68146d22de,librevm_inspector-7cdd29544501b08b,librevm_handler-b142d6eca3bb2796,librevm_precompile-c62d1dcdaf4bc1e5,libaurora_engine_modexp-0ba8df7251887310,libripemd-417bcd35c391bcd5,libark_bn254-7ef093303d196548,libark_bls12_381-a487949cedbd0e5b,libark_ec-1b932feeea52883e,libark_poly-c824d5ce4a4374bf,libitertools-fd4a39a5ad1e296a,libark_ff-deb18d6d7a393d2e,libark_serialize-0d6ae6b43bc9799f,libnum_bigint-36e6ea2a6a8e33ef,libnum_integer-11d4c76cb9b247f6,libark_std-5032f37f2d3b2b91,libp256-45d99f7243b9a843,libprimeorder-c3bbd7b5bb68864d,librevm_interpreter-a7a7c86196c8bdfb,librevm_database-58847143b01a5936,librevm_context-730c3b32d3568b36,librevm_context_interface-e1916f254f27e227,liballoy_eip7702-521fb5a85132b6ed,liballoy_eip2930-044a3e984518b4ec,librevm_database_interface-9da37e9bc64fb891,librevm_state-ba01331c5c6f00cb,librevm_bytecode-c0c030cc755d5495,librevm_primitives-b503c45cb8a525c8,libnum_enum-3953549d8910665c,libpallet_revive_uapi-cd600c931423935d,libpolkavm-f130e1c82822d046,libpolkavm_linux_raw-2ce04205196bddc6,libpolkavm_common-9e973409993bf750,libblake3-2def646c1bfa809b,libpolkavm_assembler-11d7455f005e4d7f,libethereum_standards-12067a0b2fd3298a,liballoy_core-487be948788ffe71,liballoy_sol_types-36240b87d3f4c907,liballoy_primitives-1d1a460d51a62615,libconst_hex-8fd75b3103ceca89,libderive_more-94b66af201529ace,libruint-01b4bff7d247d058,liballoy_rlp-3c1430c620e35075,libtiny_keccak-898f87eb65ef1e10,libpallet_assets-6fa190848967e40c,libpolkadot_runtime_common-3ed40b7c8491e761,libpallet_staking_reward_fn-b6b3bae830b82b55,libpallet_election_provider_multi_phase-a05b7b8de05965fc,libslot_range_helper-7daa8e4527e38428,libpallet_staking-7203965655d2653a,libframe_election_provider_support-da46edc1591dc60d,libsp_npos_elections-b0d39993f26ef93e,libstaging_xcm_builder-1a03e4ecae7825df,libpallet_asset_conversion-8aa1de4a23a84aaa,libpallet_treasury-59435c19d2cbd678,libpallet_identity-52e6fccbe0a3fd8c,libenumflags2-cdc4e568da82c520,libpolkadot_runtime_parachains-cd3432167f8dc8d9,libpallet_authority_discovery-20755560956ae09d,libpallet_babe-167b6acf42ff6219,libpallet_timestamp-3f7a6242a15a6c48,libsp_consensus_babe-79f9f3ee8dc4738b,libpolkadot_runtime_metrics-315e65ff1871ab30,libpallet_broker-13bd84ff9f888711,libpallet_message_queue-ee29a5ff311a6afc,libstaging_xcm_executor-c687503096088d51,libpallet_collator_selection-ef5586421168c251,libpallet_authorship-4d48f568017dea43,libpallet_balances-cf708ca83b476844,libpallet_session-ac8d11c2237823c7,libsp_session-21a93b9cfcb6eb50,libpallet_asset_tx_payment-260fd9dd35d290bc,libpallet_transaction_payment-ccf4fe51870e7d9c,libframe_system-c9a38960040d6df3,libcumulus_primitives_core-a8921c8812559f73,libstaging_xcm-ae1c2da371822303,libframe_support-5d9cd7816eac9ebf,libsp_genesis_builder-6d054f8fa52f48ba,libmacro_magic-ada2aa569e7c5609,libk256-a2dc8fc7c5aed5ec,libecdsa-d1999317155b37ad,librfc6979-373b20bb5c492ee0,libelliptic_curve-3e2fc9f4af03fe25,libpkcs8-35717fbfbfd16d38,libspki-98027fbbd5502417,libsec1-2ae4b5c97044444f,libder-d1a606222063ef0e,libcrypto_bigint-8ab53202d66908b4,libserdect-b51e228fa4d92fac,libbase16ct-87f42de90d943cb7,libgroup-e90f15dc95fa0204,libff-6dc804031e274b50,libtt_call-afc16e1067b6829c,libserde_json-aedc8db168a91349,libryu-fe9c9d53610fe37f,libpolkadot_primitives-a771377d572f5cf0,libhex_literal-f48c80d3a110e16a,libsp_staking-2a61ee3548041b40,libsp_consensus_slots-df4350efd291bafe,libsp_timestamp-7db059f874622448,libsp_authority_discovery-5f237ff8a51d6d3f,libsp_api-0aec8f7aff01d31b,libsp_version-bf15d6160db1507a,libparity_wasm-82171680d3dfcc53,libsp_metadata_ir-6392c4c864f81e59,libframe_metadata-bfe5db1e8d736325,libsp_inherents-7a4ead564f998aa4,libpolkadot_parachain_primitives-1e04dacbc056817a,libpolkadot_core_primitives-af3c7c33100cc301,libsp_runtime-fc88dff3c8128b0c,libsimple_mermaid-420519fe3f84846f,libtuplex-5bf6a2b2430ee1e0,libbinary_merkle_tree-9ed36a0945dfc099,libsp_weights-19b3ad54a44a0e82,libsp_application_crypto-f6ffc397ceb9c6ac,libsp_io-d1b7a66871914230,libsp_state_machine-7d98e46287b37153,libsp_panic_handler-e77a9f7c393da669,libbacktrace-bba5e8e844286e7a,libminiz_oxide-b4a1aa841b4dfb7a,libadler2-33550890a7312286,libobject-e26a68ce4c5ea20a,libaddr2line-bfb9fd0c6c2e942c,libgimli-15a114df80fc5ef2,libed25519_dalek-3535dc11f778c1f2,libsp_runtime_interface-7a63b1674e25f1ab,libsp_tracing-28207ad0f1bac176,libregex-28670936e59fd168,libtracing_subscriber-fa43b871e4de9bf8,libtime-ace246a37ce0b272,libtime_core-1b16d34070cadc9b,libnum_conv-d135835accaa5a99,libderanged-933b5fc24e49f5d3,libpowerfmt-d18881c0ef5e5908,libsharded_slab-3c606343e8050abc,libmatchers-76e9c6625b1cfd1c,libregex_automata-7d44f6a7b14c352b,libaho_corasick-dc5cd0eec96ac60c,libregex_syntax-dde8c4b85c538301,libnu_ansi_term-b1d7565f8ce76f3b,libthread_local-130152826a260d09,libtracing_log-a6a76509997a8886,libsp_wasm_interface-59b2dcc8209570f8,libwasmtime-e04ebe01b128fed8,libwasmtime_internal_cranelift-64aadd8796ffe105,libcranelift_native-4a8b30a3e2ebcd0e,libitertools-e2d427c12e51d61e,libcranelift_frontend-e237c382892794e7,libmemfd-89a797fb208fbbe2,libaddr2line-18a4416d20b0f572,librayon-87d35f539c3da3d8,librayon_core-bfcf2608f8d84375,libcrossbeam_deque-55138d1195a1da55,libcrossbeam_epoch-c9e51653b9caf046,libcrossbeam_utils-2c3658618ab7e35c,libwasmtime_internal_cache-e52ce989bb24be37,librustix-d198bc87615be56a,liblinux_raw_sys-e135efbd3e3fe5d9,liberrno-e3ba131b81c86387,libtoml-315312d3905e6214,libtoml_edit-7365e738add3a384,libserde_spanned-60492e929789bdb1,libwinnow-7416c4fe02ee7c8f,libtoml_write-2f70cec7092111d6,libtoml_datetime-a2983d9e2343d278,libzstd-708e03e990890883,libzstd_safe-60b239c0c39f1a09,libzstd_sys-ea39aaff3cf08c75,libdirectories_next-3e10fa5ae23ed4d2,libdirs_sys_next-b09024ce5d1b1e1a,libwasmtime_internal_unwinder-e27d6bb61f000747,libcranelift_codegen-b076792ee90a8535,libpulley_interpreter-4714992310f24356,libwasmtime_internal_math-b4b3a1417633824b,liblibm-4566692a50e624f7,libcranelift_assembler_x64-df2e303681c6e136,libcranelift_codegen_shared-1585f2d4823cae98,libregalloc2-3c35839cbe9989e6,libbumpalo-0c0bb1e45492f21b,librustc_hash-a6a5f22ae3012af2,libcranelift_control-b971812337d54826,libarbitrary-a718c353f23dba02,libcranelift_bforest-25bf0a2c5329720f,libwasmtime_internal_slab-3a91f07415d59cdd,libwasmtime_internal_jit_icache_coherence-bfb728fbeb020424,libwasmtime_environ-d71f06056ea60533,libpostcard-513dbf929b54c229,libcobs-6b1dee9d5bdea72f,libthiserror-39866092b054b09c,libgimli-296da9a8e50f49fd,libstable_deref_trait-03a87de40f153b67,libcpp_demangle-7860fc8072937f8f,librustc_demangle-eb72f1434c999a2e,libcranelift_entity-21b0a26e7871f8be,libcranelift_bitset-30f03b9720f06a49,libtarget_lexicon-c2bd6375b0365d2b,libobject-1f62e4bb9bdfcf6c,libcrc32fast-5811dc940a79c3d7,libwasmparser-0d7d96b4a3efe052,libbitflags-cb13569cd6b97c6f,libsemver-0df01d808a3dc06d,libanyhow-fd7b773a4765faf1,libsp_trie-8e67b1792d574aac,libtrie_root-cd6fccdd6340cdbd,libmemory_db-c5e6dbaf13c26f6b,libsubstrate_prometheus_endpoint-5c12b9a7900d09b8,libhyper_util-5a5cd5b44aec4b70,libtower_service-4a35c7c879daed89,libhttp_body_util-b034e1cb8dd08200,libhyper-95656c8d4f58519a,libwant-f3064d012c3d8066,libtry_lock-4f18628be3bbaced,libhttparse-f4fbd609b213ab40,libh2-30c381f3d58088c5,libindexmap-0b164182d0f31114,libhashbrown-69d519db1601cad7,libfoldhash-0b9d50b2e21e990b,libtokio_util-622d9a83be00716f,libtokio-023e50e7b8f61caa,libsignal_hook_registry-17b0963998dd1c5e,libsocket2-7ff2b403cc9ab9c4,libmio-0b9122e33b758f72,libatomic_waker-73af6e92a6f9ca54,libhttpdate-7d950dda6b89b92e,libhttp_body-9b96f6c6db882063,libhttp-eba3e9adb29bc43c,libprometheus-3132206ee938c463,liblazy_static-8f0b3132db032b6c,libspin-89557400fc372acb,libfnv-6355be18973380fc,libschnellru-f61378d03ee3c3cc,libhashbrown-3919c8818bc67eb3,libahash-fad662209da8ecf3,libgetrandom-e3e91c8775010ef5,libnohash_hasher-6b4cb1f5f42a640e,libtrie_db-cc2b1be7b016992f,libsp_keystore-8c471e435fcb97b0,libsp_arithmetic-1f37f6cd439bac9e,libdocify-1a6de6568abfbcd2,libsp_core-8e69305c26e1fb38,liblibsecp256k1-7e1f72cdb64b9fd8,libbase64-a02c8cb3bef2dd16,liblibsecp256k1_core-f636853577d73283,libdigest-9fe19cea8e21f97b,libfutures-fd178f914b1786b0,libfutures_executor-e471f8cbb5493e7c,libnum_cpus-a089d499910a76de,libfutures_util-1e83564de5be0253,libmemchr-c4a665a7c83181c8,libfutures_io-5c9a7556f82e64ae,libslab-3976d52efe25b86c,libfutures_channel-361f1393442e6b1d,libfutures_sink-4b250c9771a2bac6,libfutures_task-218b0bcc6b4e1621,libpin_utils-cf0786e8d78ab232,libfutures_core-3ae1894eb35020e3,libsubstrate_bip39-3f781c74f2930989,libpbkdf2-6e4e12766b658762,libpassword_hash-d166635faff0baa4,libbase64ct-3ae0299f90296ac6,libhmac-b1120193b5d4219b,libarray_bytes-063d4ca0da8d5687,libbs58-7a0b1dd6106f11fe,libdyn_clone-9f161e920f7ec21f,libbitflags-fb640c373b942643,libtracing-c177af3cd9b7f9f9,libpin_project_lite-9517b556e393a166,libtracing_core-fe0d82b5893977f6,libonce_cell-088dfaabe810f05c,libportable_atomic-c193d425a287f4e4,libthiserror-7d15a1ccb91a03dc,libschnorrkel-d84bf99b9a148171,libmerlin-642993f1839bad45,libgetrandom_or_panic-a14af6e7907a82a9,libed25519_zebra-f15eb5286761cee1,libed25519-5876f4a1b69ef465,libsignature-47b3304c4246685e,libhashbrown-1daa3dee80ffc00f,libfoldhash-52b6f728cd5804eb,libequivalent-170498df83b1c24c,liballocator_api2-ef192bfeedac586f,libcurve25519_dalek-fa8e45b2e1e3c0c1,libsecp256k1-5478ab858dfc8ae0,libsecp256k1_sys-25a32dd497bc2cdc,libsp_externalities-34dc5eb6902cdb8c,libenvironmental-d46df894c447337e,libsp_storage-3370a0074202cbe6,libref_cast-6cc1f74b7ce09c6f,libsp_std-6c1f3c19ff2df05d,libparking_lot-203f1d6c1a2f5d6a,libparking_lot_core-a0e022d63d6a3f94,libsmallvec-f0034f5e656e2895,liblock_api-9d5755e99b3dc9cd,libscopeguard-ec560f87cd1e1afd,libhash_db-2808f669f282810a,libhash256_std_hasher-6cd3d686220c8adc,libprimitive_types-af1255d3d381da7a,libimpl_rlp-3700375fa38ade91,librlp-38db2fa0ccf769a7,libimpl_codec-10a800319d763a5d,libimpl_num_traits-296d69b2e6fab726,libinteger_sqrt-3a57d76cd88cfc6f,libnum_traits-724326b6a4161cbc,libuint-2a9899580f912a58,libcrunchy-a95295e487403c45,libhex-ca165d8c548dda07,libfixed_hash-63be3905af453b3f,librustc_hex-5efafc13c6f47047,libblake2-bf5602bb94ebb6cf,libss58_registry-f1c4bb4fbc681fc8,libnum_format-e3cc4b5791d06296,libitoa-6f50db13f6b9e08f,libsecrecy-a0ced12c09642213,libitertools-06c738f260604af0,libeither-07a3a480f9bf64de,libparity_bip39-47c925e915c1fab6,libunicode_normalization-d4d97d4bca2c03b9,libtinyvec-ee51b41f22a7c11f,libtinyvec_macros-bd057d1890e153d7,libbitcoin_hashes-052e08a5496e3508,libhex_conservative-342127af8c5ca4f5,libsp_crypto_hashing-e04d7c9c81b89c38,libsha2-c05e7209bd6502e9,libcpufeatures-6e9b62d8345c306e,libsha3-fe8954f06f112ff5,libkeccak-9829091b4d1783d2,libtwox_hash-54d76b108df3e1f4,librand-bb05ef44f0f99b62,librand_chacha-0c728b8559a6b5ba,libppv_lite86-7c3995ee204bb988,libzerocopy-b2975503558e03b1,libstatic_assertions-f30b05a76518059f,libblake2b_simd-409e526484a6762d,libconstant_time_eq-ba634f25521f95c3,libarrayref-19431fccf0712618,libdigest-f441201150da6a91,libsubtle-7267faf851c85054,libconst_oid-1fa36c398b425196,libblock_buffer-918b2a4e07a1fa9e,libcrypto_common-4d9408784844dd08,libgeneric_array-635a0a1de7795ef3,libtypenum-8bfc693bcacea3fd,libzeroize-b458a146e61c2bb6,librand_core-bd75ef4c07d154ff,libgetrandom-d35f02d2471bc7fd,liblibc-b44f10b30af41aad,libbyteorder-6d90da58f41ca365,libimpl_serde-b168e22d0a0dab68,libbounded_collections-50bb2cb720100e59,liblog-91b5059d23fce8e0,libjam_codec-be9b36f88a230a6a,libscale_info-8f7564ed91e88a62,libderive_more-2aa0ffbb315dd458,libcfg_if-d06196730a2c709f,libparity_scale_codec-366020d22e5a5b94,libarrayvec-3357df8f8c25dfde,libbytes-095cee7e5476ae65,libbyte_slice_cast-fb5483dcd7f92eb3,libbitvec-acf289c6a997505b,libserde-21e33667da8711ca,libserde_core-34b9c683c6b60b76,libwyz-4662ddbfabbece48,libtap-c7d4206de6d92d5b,libradium-3fd83693e63f8b3a,libfunty-02638f34e69e4b3a,libconst_format-40b72ba4abbb2bdf}.rlib" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib/{libstd-*,libpanic_unwind-*,libobject-*,libmemchr-*,libaddr2line-*,libgimli-*,libcfg_if-*,librustc_demangle-*,libstd_detect-*,libhashbrown-*,librustc_std_workspace_alloc-*,libminiz_oxide-*,libadler2-*,libunwind-*,liblibc-*,librustc_std_workspace_core-*,liballoc-*,libcore-*,libcompiler_builtins-*}.rlib" "-Wl,-Bdynamic" "-lstdc++" "-lstdc++" "-lgcc_s" "-lutil" "-lrt" "-lpthread" "-lm" "-ldl" "-lc" "-L" "/tmp/rustcr8cBgr/raw-dylibs" "-B<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/bin/gcc-ld" "-fuse-ld=lld" "-Wl,--eh-frame-hdr" "-Wl,-z,noexecstack" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/secp256k1-sys-4f93b062f00e1d31/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/wasmtime-9b04fcaed6b9cbdc/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/zstd-sys-792dc1b8f18b6dfb/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/blake3-e15c142d04376528/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/secp256k1-sys-5b1b17391b95b067/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/librocksdb-sys-3cc3a72fc4d653f2/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/tikv-jemalloc-sys-20d05c2403dfaec9/out/build/lib" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/lz4-sys-0cf7d07a9f97fbe7/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/ring-85499d409e198c3a/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/libsqlite3-sys-434120d1c0da2b20/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/wasm-opt-cxx-sys-30847dd6066cbafa/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/cxx-026061f434119f42/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/link-cplusplus-07f5fa53e418f2f8/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/wasm-opt-sys-b50fd0c944cfd971/out" "-L" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib" "-o" "/home/ubuntu/DePow/blockchain/target/debug/deps/pallet_fee_delegation-cc0d31d946b68345" "-Wl,--gc-sections" "-pie" "-Wl,-z,relro,-z,now" "-nodefaultlibs"
  = note: some arguments are omitted. use `--verbose` to show all linker arguments
  = note: collect2: fatal error: ld terminated with signal 9 [Killed]
          compilation terminated.
          

error: could not compile `pallet-fee-delegation` (lib test) due to 1 previous error
warning: build failed, waiting for other jobs to finish...
error: linking with `cc` failed: exit status: 1
  |
  = note:  "cc" "-m64" "/tmp/rustcriVVjV/symbols.o" "<108 object files omitted>" "-Wl,--as-needed" "-Wl,-Bstatic" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib/{libtest-*,libgetopts-*}.rlib" "/home/ubuntu/DePow/blockchain/target/debug/deps/{libdepow_primitives-9ca81cde990ba35c,libpolkadot_sdk-98af269c44f60536,libsubstrate_wasm_builder-16088889cc02d34d,libjobserver-ebb3010277890062,libpolkavm_linker-b8b75b8be7119dbf,libdirs-0e6f1e42452572e3,libregalloc2-029b251ef8be94d0,libslice_group_by-f1fedd16c3ecbe49,libshlex-834e721b3c6c6a50,libfiletime-896c40975e64fdcd,libwasm_opt-785acc795f747f0a,libwasm_opt_cxx_sys-16bad0093342946f,libwasm_opt_sys-e082691d989a5c45,libcxx-49d8e88983791154,liblink_cplusplus-87df92ec8539cf6c,libwalkdir-5b17f7d93ab63aa9,libsame_file-7c8ad0c8c9fe0e05,libcargo_metadata-0d632bd30baecabf,libcargo_platform-b4dbe4809d079bb6,libcamino-0996bd698384ad86,libbuild_helper-3d072b35b20c2265,libsemver-81b661d38b005dcc,libsemver_parser-384304630514f989,libsubstrate_frame_rpc_support-9e5e2c5577ff7e67,libsubstrate_build_script_utils-f686463c69dc9652,libsubkey-7fbf5699bfa3d5f0,libstaging_node_inspect-789c81c5a5eec8d8,libsp_core_hashing_proc_macro-32d538f9b5e47ef1,libsp_core_hashing-b0ac283bad93aa23,libsc_consensus_pow-febd2a9710048995,libsp_consensus_pow-7e6f4b9fd4240ec8,libpolkadot_omni_node_lib-69b661f197829b76,libsc_network_statement-d0476080db9d3519,libcolor_print-ea403151c8715551,libsc_consensus_manual_seal-9cf79bcc3b28f961,libsc_statement_store-c85dcfd12cfce35d,libstaging_chain_spec_builder-c27c639c3260601e,libpolkadot_node_core_pvf_prepare_worker-4c4e72b042223d7e,libtikv_jemallocator-b7e42bf674ad792c,libstaging_tracking_allocator-09b1a751b79e5c3c,libpolkadot_node_core_pvf_execute_worker-333c54e87f5ad065,libpallet_sudo-9186b5652d61c6dd,libpallet_revive_eth_rpc-e45239df35a80e88,libsqlx-5d9c45ad59dbcd27,libsqlx_sqlite-81d89086e7279aee,libflume-3255ce2f0fc3840a,libserde_urlencoded-a64231c7275741f4,libfutures_intrusive-b3e1b3b0f73113fa,liblibsqlite3_sys-1f63f857be5dd60e,libatoi-34e39a99c154b103,libsqlx_core-ddc9688a229a6ff8,libhashlink-95661769fc82641e,libevent_listener-e2058512768cf4b1,libparking-d405a45bca78b675,libpallet_grandpa-c36cc11290577245,libpallet_contracts_mock_network-fbb8d4410e15508e,libpallet_contracts-1cc59ba504fb4b44,libwasmi-cb3ae6cb6ab2416a,libwasmi_collections-fe627ab73aad72ea,libstring_interner-6e92f9b99c85da39,libwasmi_core-b05b5862410a3ce0,libdowncast_rs-dfebbdb571f15c7f,libmulti_stash-0db997889556dc50,libwasmparser_nostd-b5000577541c8e84,libindexmap_nostd-3a0f12419eae3e20,libpallet_contracts_uapi-40ecd485ca1e0e50,libgenerate_bags-7ad4e5faadad3529,libframe_support_procedural_tools-ff2076ae082fbfb8,libsyn-61f3ab5d0e145bad,libquote-c00c74433ac9180f,libproc_macro2-46bda76951fa7f45,libunicode_ident-4c7da432017fce16}.rlib" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib/{libproc_macro-*,librustc_literal_escaper-*,librustc_std_workspace_std-*}.rlib" "/home/ubuntu/DePow/blockchain/target/debug/deps/{libproc_macro_crate-b0663b644d326720,libtoml_edit-d8c84f73c7ab9548,libtoml_parser-9e387b9f140b2d65,libtoml_datetime-9a39996ce0166876,libframe_remote_externalities-1de8b1f3ee3c0cb1,libtokio_retry-495ce14893d5c930,libsubstrate_rpc_client-92012465c4821574,libindicatif-0b5074783497f601,libnumber_prefix-3a2388bf1d421940,libspinners-b893dafe6a248470,libmaplit-d4165f096a57f0d7,libstrum-f0942e02b4e67f71,libemulated_integration_tests_common-17bd8adee68ece16,libpallet_whitelist-328774b0d9872c6b,libpolkadot_sdk_frame-fb85564f29b39a95,libframe_executive-51f8184729044653,libxcm_emulator-cd0281db9ac4490a,libxcm_simulator-89192a15374a82b0,libcumulus_pallet_xcm-d8ef43c272674ae0,libcumulus_pallet_aura_ext-981be51cb0253e5e,libpallet_aura-ce5f337f48d101c5,libcumulus_client_service-418c5a832415cca1,libcumulus_relay_chain_minimal_node-cc1a5a147b7b1b4e,libcumulus_relay_chain_rpc_interface-9059354811fbf44f,libcumulus_relay_chain_inprocess_interface-34d2ca462a16d04a,libpolkadot_cli-da8ed7de1ba2b0a2,libsc_storage_monitor-fd3eeb0c43844f92,libfs4-cd1383d892e93f77,librustix-163a8bb80649f972,liblinux_raw_sys-be563daf86b20b65,libpolkadot_service-61fc825a2aeb9ba7,libpolkadot_node_core_parachains_inherent-a6fa0e152a838b68,libpolkadot_rpc-66b7fbfd7aa55ff7,libsubstrate_state_trie_migration_rpc-e0e05423e85f0419,libsubstrate_frame_rpc_system-7488008b3863f668,libsc_consensus_grandpa_rpc-7d5d6353e15810f4,libsc_consensus_beefy_rpc-19bce9fbc70ecec9,libsc_consensus_babe_rpc-fc3fd50a0fc307fb,libpallet_transaction_payment_rpc-b9806ff952d268ff,libmmr_rpc-2cd80e8f2ff8b49a,libsc_consensus_beefy-beb4e994fbd06fa3,libpallet_transaction_payment_rpc_runtime_api-349bb3fe67b2d425,libframe_system_rpc_runtime_api-b1215306f3078194,libsc_sync_state_rpc-3c0cf4d83197817f,libis_executable-e08b7fa8a191c193,libpolkadot_statement_distribution-98fdb07449ee4ec9,libpolkadot_node_core_runtime_api-1c6f279718000bf8,libpolkadot_node_core_pvf_checker-dda1c4d28a71f788,libpolkadot_node_core_provisioner-a0e01f61d705f993,libpolkadot_node_core_prospective_parachains-85e95504b1ac122f,libpolkadot_node_core_chain_api-be84a94b7a403232,libpolkadot_node_core_bitfield_signing-90d9ab170b1e5c65,libpolkadot_node_core_backing-5ed288856b2c2ff4,libpolkadot_node_core_approval_voting_parallel-ffe55b7ea44ac1f5,libpolkadot_node_collation_generation-6e7a38c6299ffec9,libpolkadot_gossip_support-921b59396cc4bcbd,libpolkadot_dispute_distribution-39cd25c6192f6d52,libpolkadot_collator_protocol-1f0a4fcbaed1f745,libpolkadot_availability_bitfield_distribution-812cd9a5b8a35fb8,libpolkadot_approval_distribution-921f03457541cf46,libpolkadot_availability_distribution-8accfe39fc718f46,libpolkadot_network_bridge-e6a325b5d5253f54,libpolkadot_node_core_dispute_coordinator-c18a6050247a871c,libpolkadot_node_core_chain_selection-f55b380b4a6dc5b4,libpolkadot_node_core_candidate_validation-b33c04e7f13f4dda,libpolkadot_node_core_pvf-164fb5d81c89bf79,libslotmap-23c04bee080bb582,libpolkadot_node_core_pvf_common-814c1c3ce1b4104d,libcpu_time-62711d61d82ab9ba,libseccompiler-b10c1acf0b4d40f3,liblandlock-619169d40c41817a,libnix-ea97d5e373196ce2,libalways_assert-b83f0309eed23856,libpolkadot_node_core_av_store-2fb9a1ac01225d8d,libpolkadot_availability_recovery-75bd05d119606447,libmmr_gadget-2252a559c5d85a84,libsc_offchain-3c839c236038bd36,libthreadpool-adb90ecfa55f5451,libframe_benchmarking_cli-2d83311f0462b6a0,libgethostname-702259f180fd9a2c,libenv_filter-eb8263edf07d0cab,libframe_storage_access_test_runtime-402418997db413b8,libinflector-685fcef610d0a6c4,libframe_benchmarking-f07c9ea701b7f713,liblinregress-87ae813550f5912e,libnalgebra-7257b88717810b69,libmatrixmultiply-7214ec51e047fb13,librawpointer-71563accd9c427ed,libsimba-7f6da60a798555b6,libwide-1ef7bb7d6579ffe8,libsafe_arch-538a7c9cf339dc81,libbytemuck-1b4bef5f338586fe,libnum_complex-5fc1f5b52802fbc1,libhandlebars-75085d734e04d7b2,libpest-0be0fc4f5936db64,libucd_trie-76c2a9515b97695d,libsubxt-9fc67705e514dc32,libsubxt_rpcs-5746c27eb094d306,libfinito-b3821ac3f44899e6,libsc_runtime_utilities-8fff403d49a27912,libcomfy_table-049bb46cc8ce6ccb,libunicode_segmentation-1ff1aec11bbc1d36,libthousands-6cda707d9bd896cc,libsc_consensus_grandpa-b768f91c3b13a9bc,libsc_network_gossip-eaa8b8c8a39b5198,libpolkadot_node_core_approval_voting-10f3c3f4ea776615,libsp_consensus_beefy-a77786d788de19c0,libsp_mmr_primitives-bee41c6862433fae,libpolkadot_ckb_merkle_mountain_range-e6d5524f9f5dc8ef,libitertools-c537e75bd0786902,libcumulus_primitives_proof_size_hostfunction-5566d83fdb28f797,libcumulus_client_consensus_relay_chain-3095dfa5330a3992,libcumulus_client_consensus_aura-530d6eaa4f9f8777,libpolkadot_node_subsystem_util-f7bdfe54552bfe1a,libpolkadot_erasure_coding-044c57bef760b53d,libreed_solomon_novelpoly-8c473a9717f440f5,libcumulus_primitives_aura-d0cef32a609c53f9,libcumulus_client_parachain_inherent-8fa97278fc2f8ad4,libcumulus_client_consensus_proposer-b1a8f81132ba57cb,libsc_basic_authorship-35aa3df91ba74b3c,libsc_proposer_metrics-3e0d5ea48f60cd9d,libsc_block_builder-c5fadfb8642fdaa0,libsc_consensus_aura-3fa123208fe4fa18,libcumulus_client_collator-c3d3a1c872147e53,libcumulus_client_network-0ad9b563c89bad50,libcumulus_client_consensus_common-2bb1fa0e75945806,libsc_consensus_babe-f693f882b6a5250b,libnum_rational-b7d8474f5da7b7d9,libsp_block_builder-f591ec64fa34b937,libsc_consensus_slots-be0e5a480a150667,libsc_consensus_epochs-60921b692815857a,libcumulus_client_pov_recovery-ccff7272ed8d61d4,libcumulus_relay_chain_streams-1397c3f93ecb2f58,libpolkadot_node_subsystem-3869ca286ffd27be,libcumulus_client_cli-ade69bac3091d9e0,libcumulus_client_bootnodes-acfa282c2521ef84,libcumulus_relay_chain_interface-8c7923def20f915f,libpolkadot_overseer-8e8723f4aed1bf7b,libtikv_jemalloc_ctl-77ff53f658103548,libtikv_jemalloc_sys-169974383fe1c222,libpolkadot_node_metrics-a4447f387d26c299,libsc_cli-617881c31f29d237,libfdlimit-e70d78aa6f4c71ea,librpassword-00600b3175db9e86,librtoolbox-b1acac122af90b81,libnames-11f1a9dc1501bbb9,libsc_service-e810b3a86f0f3a62,libsc_informant-2b32bd8df532a312,libsc_sysinfo-949604758bdefb0d,librand_pcg-754e2bf71d3675d6,libdirectories-0aa2f37ed02990ab,libdirs_sys-8a734b1cd4a4c53d,liboption_ext-791e6f42d0cc761e,libsp_transaction_storage_proof-7278b3a1d3f342b4,libstatic_init-cbe230b1a1a5eec2,libsc_network_transactions-4817b6a069a39930,libtracing_futures-57d7588899a791d2,libexit_future-fc8c32d741be3cb3,libsc_rpc_spec_v2-65f1403d29123abb,libsc_rpc-6770a63a55d4b037,libsp_offchain-f186f7e08dcf2501,libsc_tracing-bbe454957753471b,libis_terminal-832a0720c3701fea,libconsole-1e0cd8456b43f6da,libunicode_width-8521d0cba76a6144,libsp_statement_store-b11513be5d325b27,libaes_gcm-c8f99c1e3f9a79a8,libctr-68cb21b63042627d,libghash-db7edf2853dfd74d,libpolyval-392bd8192ba33e10,libopaque_debug-a4f012e41a473180,libuniversal_hash-6b9fbc17cad60fbd,libaes-b936a78899d86313,libcipher-e733a6dd82daeca7,libinout-3ad92d7440341fc4,libaead-d01a477925d8fce4,libsc_network_sync-7fe062ec1c490a61,libfork_tree-a6f5d40d479017f1,libsc_network_light-583f724e6337360d,libtempfile-a12820c6739866a6,libfastrand-4ca17b4d923f7d09,libsc_transaction_pool-8bbd8d5abd286c65,libsp_transaction_pool-71dbc7ab2612ead5,libsc_rpc_server-73666c5c16e8669b,libtower_http-8442a1a238c4a1fd,libsc_rpc_api-7da24ea414f9e90e,libsc_mixnet-ead843129b104948,libsp_mixnet-80ceb5f8d4bdb45a,libmixnet-0faf042c634abece,librand_distr-12b97f6a43231466,liblioness-914fa04ce2b4a83d,libblake2-713922ab3b4b6961,libcrypto_mac-fe93a091a3790567,libsubtle-4f8cf0f70c840721,libbyte_tools-e09074427588670e,libdigest-70216a37bd0ad07a,libgeneric_array-1ddc6e133bbadb35,libopaque_debug-c052b5c53791eb7b,libchacha-0faa30e49d1eecb1,libkeystream-6130d4eca8f38966,libc2_chacha-ed32c4795681230d,libcipher-19b758b714c1d8bf,libhashlink-6973fd2fdc936780,libsp_rpc-c7e51538f8a24a41,librustc_hash-3b79e8232350cf3a,libforwarded_header_value-a9ed985beaf120d6,libnonempty-9955b59286e94ad5,libgovernor-a4d03c068f4c2bb2,libquanta-0081e4108a7de9d1,libraw_cpuid-0bdec824ffd50b87,libdashmap-6560c1e0918d84fe,libnonzero_ext-d0b45501736186dc,libno_std_compat-e24ca93c350860e6,libsc_client_db-f938444ea3a8046d,libsysinfo-97b4f1294ec134d7,libparity_db-ae05db5e9ab5944c,libmemmap2-fcda6c9fe40329ab,libsnap-9898a1475d0500a7,liblz4-a5ae754b204ee8bd,liblz4_sys-a7f00bbdf772e355,libfs2-4161a679f17279f4,libsiphasher-98cfd176f882e3dc,libkvdb_memorydb-4dc310f0a97116c6,libsc_state_db-21b7427b89091bfd,libkvdb_rocksdb-640095fd38ee254d,librocksdb-ab4871e0ef253f9d,liblibrocksdb_sys-d1dd1e8c27ad77b2,libjsonrpsee-53f719d098aeff2b,libjsonrpsee_server-0478a9efd8180b5a,libroute_recognizer-57f8b40c07be09d2,libjsonrpsee_wasm_client-0b8a9c0cde1b850e,libjsonrpsee_ws_client-79bee8187cc46bd7,libjsonrpsee_client_transport-2730da86c9f54c41,libjsonrpsee_http_client-8f75788356e89d29,libhyper_rustls-130846b613af2374,librustls_platform_verifier-69fe32cedbb2f168,libtower-0d4102323bdec6db,libtower_layer-9ce6944a7b9fbe04,libjsonrpsee_core-63fedc73192e85fd,libjsonrpsee_types-4caca39546c18d53,libsc_chain_spec-c2c861426097edfa,libmemmap2-51c73a5ce8e39c3e,libclap-b56f5f05180050ed,libclap_builder-abe11c3255cb7cf0,libterminal_size-35c71ac979547937,libstrsim-08f9beca88bc3385,libanstream-9fd87b725ebcde9e,libanstyle_query-6aac056c348ee6b5,libis_terminal_polyfill-8eb15715dd1b4348,libcolorchoice-280757403274d424,libanstyle_parse-e92232a5ceecc849,libutf8parse-f8f3d52be9bca96f,libclap_lex-44a32cc27246fa49,libsc_telemetry-f5adcda9cd9c82be,libchrono-e9d2f620c7fd696a,libiana_time_zone-1812bd8a2108aee5,libsc_consensus-501a4a8f122c9317,libmockall-40d404cbff822eee,libpredicates_tree-d9609af0867c6f02,libtermtree-34073be187be5c13,libpredicates-9a10da274941e6ed,libanstyle-b0b8596b0b7b1c75,libpredicates_core-6a7b6ab0719e5ece,libfragile-f8121a397221fa3c,libdowncast-0af1872d6ada3e76,libpolkadot_node_subsystem_types-deecdefeda48ce3b,libpolkadot_statement_table-3507194da9c27038,libpolkadot_node_network_protocol-7fd88596e4b67508,libtracing_gum-ff1263935764acf5,libsc_authority_discovery-135df533c5e65e7e,libpolkadot_node_primitives-4e2db19203ccdc59,libsc_keystore-6205ed64d208bd63,libbounded_vec-6619b7c55b732bc9,libsc_network-68537f7200dd9992,libpartial_sort-6208e275ff793520,liblinked_hash_set-99cd858f315294ea,libwasm_timer-8aecfda2cf706b85,libip_network-0c35901f3c60366d,libsc_network_common-4b845f4408d2cf95,libsc_network_types-85ed5e3cf4fcbc46,libserde_with-3585f6812f200680,liblitep2p-819dd6acf195b293,libtokio_tungstenite-8281214384d0e8f8,librustls_native_certs-31e97ea40e75a57d,libopenssl_probe-9783bab9077d4fa4,libtokio_rustls-a4750db20bfb3101,libtungstenite-7a4a3a4c91003e41,libutf8-ae9b530d9f927b7a,libnetwork_interface-6324ad6d05e06297,libsimple_dns-ec9b1e4bbcadd2e5,libtokio_stream-9bab457febb12bd5,libcid-d0ea55ce112945ac,libprost-14e383d06ff889df,libmultiaddr-88a0f85a9253673f,libhickory_resolver-1c95d73c3b55d55c,libmoka-d3f79e0e3de0cda3,libtagptr-5e403d8a8e203790,libuuid-c21f09d12dada164,libcrossbeam_channel-dd0d55d496c6a2dd,libhickory_proto-f6f1b07bbcf0726a,libprost-67b52e821ee3894c,libcid-5fb3ee6bc1f46395,libmultihash-81825dc7509dd421,libblake2s_simd-853b74eb11486903,liblibp2p-077200c1091326c3,liblibp2p_yamux-0178e07852d92a88,libyamux-93420f44329ce5be,librand-f06af8018277d0e4,librand_chacha-d52e9d4a5654ff3c,librand_core-51a983d5e036e22b,libyamux-efc8946cfc3db037,liblibp2p_websocket-cf133fd184e01a91,libwebpki_roots-4a063c340e3691b3,libsoketto-aa527d60586841fb,libsha1-9b6e48af92b27617,libfutures_rustls-858d07dcd79ac854,librustls-b17913d19adb7e82,libwebpki-08ac281bc733918b,librustls_pki_types-e1b44771807811b1,liblibp2p_tcp-9601eb44ba42cfc5,liblibp2p_request_response-f566a57abae2683f,liblibp2p_ping-cf853c8210a51463,liblibp2p_noise-3ae9a795bd751f87,libx25519_dalek-15918086da2a5eee,libsnow-60b0c74d6f1f74b0,libring-7cddbc7071df080b,libuntrusted-8e652868e2848723,liblibp2p_mdns-a822113a6f0cc725,libif_watch-ffe3951da6cd637e,librtnetlink-a1e86ead4887a805,libnix-4ffd077e84a3bd8a,libnetlink_proto-0a28b5d3a902907f,libnetlink_sys-f7229f614fc0a3f7,libnetlink_packet_route-1e1629c15f26134f,libnetlink_packet_core-6177e9280b4d5a32,libnetlink_packet_utils-89d685a0ae829635,liblibp2p_kad-976441a58bfc8bf1,libuint-b9ff1d0af369505a,liblibp2p_identify-25f0f6a67693dbb9,libquick_protobuf_codec-3f724cc82898dc7b,libasynchronous_codec-d1a241bd8d427dd1,libfutures_bounded-b0eafce5414c01d6,liblibp2p_dns-204e19526bb0e920,libhickory_resolver-a70ef5bcdbab5705,libresolv_conf-778c371bdaadf6e7,liblru_cache-71e1a12f023870ba,liblinked_hash_map-1f38cde25ce3ffb8,libhickory_proto-c618635e9d4cb20a,libipnet-8e7cc3128782b543,libsocket2-b767b61e31f987da,liblibp2p_connection_limits-623a9c8e5064f86c,liblibp2p_allow_block_list-7f1347ae877ad395,liblibp2p_swarm-cd5a98353a0ac193,liblru-01cd6db15c1e9ab9,liblibp2p_core-650a1cdfa4e3c49e,libvoid-665039f8d4982a3d,libmultistream_select-a0b19df2e050d806,libunsigned_varint-c145f9534d0a7304,libasynchronous_codec-88be3c20880d7c3f,librw_stream_sink-284cff33ee71cd59,libweb_time-c24f3924985c7cb0,libmultiaddr-bc2c232bed946809,liburl-6157bb0125fe4e5d,libidna-3960f71eb1dcc62f,libutf8_iter-b6eaad6a6b2fc516,libidna_adapter-161525d08d8b5f75,libicu_properties-66e73f661faf16a9,libicu_properties_data-4c634182aa4f34d3,libicu_normalizer-f1dead93511c1be9,libicu_normalizer_data-9c4482b1e712a920,libicu_collections-bff15b1e2c8cb5e3,libpotential_utf-8b59145a4536cc14,libicu_provider-5668527c1f565249,libicu_locale_core-b9649ee7bab72786,libtinystr-503262d1a623f258,liblitemap-e161d9b2525d473e,libwriteable-a9b193e6be952911,libzerovec-757266703d2096fd,libzerotrie-0b4c45137bc32aac,libyoke-dcad382880fc8545,libzerofrom-feeb5e82b24346ef,libform_urlencoded-cfe4e7600c682b7a,libpercent_encoding-3d996758cd54bd6a,libmultibase-2f795cec8fd398e2,libbase_x-6d221b3416d255ab,libdata_encoding_macro-bfb8d7e513104098,liblibp2p_identity-c342d0ac6ee7a738,libhkdf-8701e69b969ad37f,libquick_protobuf-6a2650343cc1821c,libdata_encoding-18cc8d1e9d901793,libmultihash-725662b83cb1d4cf,libunsigned_varint-8db1f362a8452bf4,libfatality-57b1949a88d5dee0,liborchestra-664f537706f1fb74,libpin_project-51f5e5545bc5d33f,libdyn_clonable-8f2fc3b6a0354c2a,libprioritized_metered_channel-00364bcaee5bffd3,libcrossbeam_queue-691d966a2dbc5b91,libnanorand-1fd5b72fcf8af371,libcoarsetime-0c7bc23528a09b43,libsc_client_api-900226c217229a7e,libsc_utils-e808493d3e25603a,libfutures_timer-fae54f90ea4d8e58,libasync_channel-c293c6624a5dcb92,libevent_listener-b8603b37c20ef028,libconcurrent_queue-a378371ece4fa662,libsc_transaction_pool_api-8a89adca4f68f423,libsp_blockchain-f49c89b78f1f33b2,libsp_database-49f1773bdb64d41d,libkvdb-62a2dc0cf6e233c4,libsc_executor-aa9831b2d7435981,libsc_executor_polkavm-8f210805e8edf164,libsc_executor_wasmtime-460ea18065a6aa62,libsc_executor_common-6d5b32d5b5fdb8e1,libsc_allocator-0352e5cb7c5edf90,libsp_maybe_compressed_blob-6f823b4e70f2d7ad,libzstd-a7b8a9c1ba77eeb6,libzstd_safe-fc73518c36abae29,libwasm_instrument-079d8ab36d81084d,libpolkavm-ba501f283070021e,libpolkavm_common-964a8a509f84af4b,libpolkavm_assembler-6065c622e0569928,libsp_consensus-79bc853b60f79254,libbridge_hub_test_utils-ff1ff49baa3c8bea,libpallet_bridge_relayers-4359431d81fb2674,libbp_test_utils-b9235019f5fb5e5d,libpallet_xcm_bridge_hub-9f4a91706f04b686,libbp_xcm_bridge_hub-ac4d56459095d975,libpallet_bridge_parachains-e5a7e6f433ee33a9,libpallet_bridge_grandpa-869fbfaefd4b71d2,libsp_keyring-404ef77b08770e2b,libstrum-6c0270af34b95a10,libpallet_bridge_messages-e93020dfc742112b,libbp_relayers-df458f05d13ebcf7,libpallet_utility-2385b6c3bc417935,libbp_parachains-53be9c96dc9c788e,libbp_polkadot_core-4cbcfb9b6c6426a7,libbp_messages-8cf1365d3c930aaa,libbp_header_chain-ebd9db8dce8fd96a,libsp_consensus_grandpa-10ee968b325ceac9,libfinality_grandpa-3c216d60605c512f,libbp_runtime-41550dd63c18cec0,libasset_test_utils-e6433a05cf2fa6c8,libpallet_xcm_bridge_hub_router-43f09f4dda26c8e5,libbp_xcm_bridge_hub_router-fbbfb6c14c168faf,libparachains_runtimes_test_utils-c39676f9578b143a,libcumulus_pallet_xcmp_queue-5e3419615220d4c6,libapprox-53a002ee2eee6999,libcumulus_test_relay_sproof_builder-caddff293ae4efd1,libcumulus_pallet_parachain_system-cb3941f7e776df51,libcumulus_primitives_parachain_inherent-60ef439f90d48b81,libparachains_common-d81e5095bc9c25ee,libsp_consensus_aura-d966ced116189686,libstaging_parachain_info-e47702873c6abf92,libcumulus_primitives_utility-16d877c25defb228,libpallet_xcm-ae85c9b3e47e0830,libxcm_runtime_apis-94ccc079572852a8,libpallet_revive-fe26c525329e5f64,libsubxt_signer-d09ce48c035f0fcc,libbip32-1c1e8e9121cfe71f,libbip39-cbe6525dd6e3c83e,libsecp256k1-378632ccbbd1e7de,libsecp256k1_sys-ff6cb74119fa46c7,libsubxt_core-9e67c5ed68eb9a92,libkeccak_hash-76f767213f676c21,libscale_value-78dd67e1c01c7a75,libyap-8a248b835730274f,libbase58-88e3c929f414888c,libscale_encode-7c30901679167bf4,libsubxt_metadata-e4b8b48a867692a0,libhashbrown-1a3e82099a6bf33a,libframe_metadata-323ecdfad054d668,libframe_decode-ad0e9e5561f14a4f,libscale_decode-a4bb95774f94d0be,libscale_bits-eca687787275f89e,libframe_metadata-13fe43588b0484a5,libscale_type_resolver-4e96d99014db22c8,libsecrecy-8f7962d09cb48b6e,libhumantime_serde-fb79af18f3656551,libhumantime-8b27791cf870d0e2,libsubstrate_bn-cec7282c7f14427c,libethereum_types-85e3a9bb5f337349,libethbloom-ec0d9cfe0b6d7870,librevm-6da0fa68146d22de,librevm_inspector-7cdd29544501b08b,librevm_handler-b142d6eca3bb2796,librevm_precompile-c62d1dcdaf4bc1e5,libaurora_engine_modexp-0ba8df7251887310,libripemd-417bcd35c391bcd5,libark_bn254-7ef093303d196548,libark_bls12_381-a487949cedbd0e5b,libark_ec-1b932feeea52883e,libark_poly-c824d5ce4a4374bf,libitertools-fd4a39a5ad1e296a,libark_ff-deb18d6d7a393d2e,libark_serialize-0d6ae6b43bc9799f,libnum_bigint-36e6ea2a6a8e33ef,libnum_integer-11d4c76cb9b247f6,libark_std-5032f37f2d3b2b91,libp256-45d99f7243b9a843,libprimeorder-c3bbd7b5bb68864d,librevm_interpreter-a7a7c86196c8bdfb,librevm_database-58847143b01a5936,librevm_context-730c3b32d3568b36,librevm_context_interface-e1916f254f27e227,liballoy_eip7702-521fb5a85132b6ed,liballoy_eip2930-044a3e984518b4ec,librevm_database_interface-9da37e9bc64fb891,librevm_state-ba01331c5c6f00cb,librevm_bytecode-c0c030cc755d5495,librevm_primitives-b503c45cb8a525c8,libnum_enum-3953549d8910665c,libpallet_revive_uapi-cd600c931423935d,libpolkavm-f130e1c82822d046,libpolkavm_linux_raw-2ce04205196bddc6,libpolkavm_common-9e973409993bf750,libblake3-2def646c1bfa809b,libpolkavm_assembler-11d7455f005e4d7f,libethereum_standards-12067a0b2fd3298a,liballoy_core-487be948788ffe71,liballoy_sol_types-36240b87d3f4c907,liballoy_primitives-1d1a460d51a62615,libconst_hex-8fd75b3103ceca89,libderive_more-94b66af201529ace,libruint-01b4bff7d247d058,liballoy_rlp-3c1430c620e35075,libtiny_keccak-898f87eb65ef1e10,libpallet_assets-6fa190848967e40c,libpolkadot_runtime_common-3ed40b7c8491e761,libpallet_staking_reward_fn-b6b3bae830b82b55,libpallet_election_provider_multi_phase-a05b7b8de05965fc,libslot_range_helper-7daa8e4527e38428,libpallet_staking-7203965655d2653a,libframe_election_provider_support-da46edc1591dc60d,libsp_npos_elections-b0d39993f26ef93e,libstaging_xcm_builder-1a03e4ecae7825df,libpallet_asset_conversion-8aa1de4a23a84aaa,libpallet_treasury-59435c19d2cbd678,libpallet_identity-52e6fccbe0a3fd8c,libenumflags2-cdc4e568da82c520,libpolkadot_runtime_parachains-cd3432167f8dc8d9,libpallet_authority_discovery-20755560956ae09d,libpallet_babe-167b6acf42ff6219,libpallet_timestamp-3f7a6242a15a6c48,libsp_consensus_babe-79f9f3ee8dc4738b,libpolkadot_runtime_metrics-315e65ff1871ab30,libpallet_broker-13bd84ff9f888711,libpallet_message_queue-ee29a5ff311a6afc,libstaging_xcm_executor-c687503096088d51,libpallet_collator_selection-ef5586421168c251,libpallet_authorship-4d48f568017dea43,libpallet_balances-cf708ca83b476844,libpallet_session-ac8d11c2237823c7,libsp_session-21a93b9cfcb6eb50,libpallet_asset_tx_payment-260fd9dd35d290bc,libpallet_transaction_payment-ccf4fe51870e7d9c,libframe_system-c9a38960040d6df3,libcumulus_primitives_core-a8921c8812559f73,libstaging_xcm-ae1c2da371822303,libframe_support-5d9cd7816eac9ebf,libsp_genesis_builder-6d054f8fa52f48ba,libmacro_magic-ada2aa569e7c5609,libk256-a2dc8fc7c5aed5ec,libecdsa-d1999317155b37ad,librfc6979-373b20bb5c492ee0,libelliptic_curve-3e2fc9f4af03fe25,libpkcs8-35717fbfbfd16d38,libspki-98027fbbd5502417,libsec1-2ae4b5c97044444f,libder-d1a606222063ef0e,libcrypto_bigint-8ab53202d66908b4,libserdect-b51e228fa4d92fac,libbase16ct-87f42de90d943cb7,libgroup-e90f15dc95fa0204,libff-6dc804031e274b50,libtt_call-afc16e1067b6829c,libserde_json-aedc8db168a91349,libryu-fe9c9d53610fe37f,libpolkadot_primitives-a771377d572f5cf0,libhex_literal-f48c80d3a110e16a,libsp_staking-2a61ee3548041b40,libsp_consensus_slots-df4350efd291bafe,libsp_timestamp-7db059f874622448,libsp_authority_discovery-5f237ff8a51d6d3f,libsp_api-0aec8f7aff01d31b,libsp_version-bf15d6160db1507a,libparity_wasm-82171680d3dfcc53,libsp_metadata_ir-6392c4c864f81e59,libframe_metadata-bfe5db1e8d736325,libsp_inherents-7a4ead564f998aa4,libpolkadot_parachain_primitives-1e04dacbc056817a,libpolkadot_core_primitives-af3c7c33100cc301,libsp_runtime-fc88dff3c8128b0c,libsimple_mermaid-420519fe3f84846f,libtuplex-5bf6a2b2430ee1e0,libbinary_merkle_tree-9ed36a0945dfc099,libsp_weights-19b3ad54a44a0e82,libsp_application_crypto-f6ffc397ceb9c6ac,libsp_io-d1b7a66871914230,libsp_state_machine-7d98e46287b37153,libsp_panic_handler-e77a9f7c393da669,libbacktrace-bba5e8e844286e7a,libminiz_oxide-b4a1aa841b4dfb7a,libadler2-33550890a7312286,libobject-e26a68ce4c5ea20a,libaddr2line-bfb9fd0c6c2e942c,libgimli-15a114df80fc5ef2,libed25519_dalek-3535dc11f778c1f2,libsp_runtime_interface-7a63b1674e25f1ab,libsp_tracing-28207ad0f1bac176,libregex-28670936e59fd168,libtracing_subscriber-fa43b871e4de9bf8,libtime-ace246a37ce0b272,libtime_core-1b16d34070cadc9b,libnum_conv-d135835accaa5a99,libderanged-933b5fc24e49f5d3,libpowerfmt-d18881c0ef5e5908,libsharded_slab-3c606343e8050abc,libmatchers-76e9c6625b1cfd1c,libregex_automata-7d44f6a7b14c352b,libaho_corasick-dc5cd0eec96ac60c,libregex_syntax-dde8c4b85c538301,libnu_ansi_term-b1d7565f8ce76f3b,libthread_local-130152826a260d09,libtracing_log-a6a76509997a8886,libsp_wasm_interface-59b2dcc8209570f8,libwasmtime-e04ebe01b128fed8,libwasmtime_internal_cranelift-64aadd8796ffe105,libcranelift_native-4a8b30a3e2ebcd0e,libitertools-e2d427c12e51d61e,libcranelift_frontend-e237c382892794e7,libmemfd-89a797fb208fbbe2,libaddr2line-18a4416d20b0f572,librayon-87d35f539c3da3d8,librayon_core-bfcf2608f8d84375,libcrossbeam_deque-55138d1195a1da55,libcrossbeam_epoch-c9e51653b9caf046,libcrossbeam_utils-2c3658618ab7e35c,libwasmtime_internal_cache-e52ce989bb24be37,librustix-d198bc87615be56a,liblinux_raw_sys-e135efbd3e3fe5d9,liberrno-e3ba131b81c86387,libtoml-315312d3905e6214,libtoml_edit-7365e738add3a384,libserde_spanned-60492e929789bdb1,libwinnow-7416c4fe02ee7c8f,libtoml_write-2f70cec7092111d6,libtoml_datetime-a2983d9e2343d278,libzstd-708e03e990890883,libzstd_safe-60b239c0c39f1a09,libzstd_sys-ea39aaff3cf08c75,libdirectories_next-3e10fa5ae23ed4d2,libdirs_sys_next-b09024ce5d1b1e1a,libwasmtime_internal_unwinder-e27d6bb61f000747,libcranelift_codegen-b076792ee90a8535,libpulley_interpreter-4714992310f24356,libwasmtime_internal_math-b4b3a1417633824b,liblibm-4566692a50e624f7,libcranelift_assembler_x64-df2e303681c6e136,libcranelift_codegen_shared-1585f2d4823cae98,libregalloc2-3c35839cbe9989e6,libbumpalo-0c0bb1e45492f21b,librustc_hash-a6a5f22ae3012af2,libcranelift_control-b971812337d54826,libarbitrary-a718c353f23dba02,libcranelift_bforest-25bf0a2c5329720f,libwasmtime_internal_slab-3a91f07415d59cdd,libwasmtime_internal_jit_icache_coherence-bfb728fbeb020424,libwasmtime_environ-d71f06056ea60533,libpostcard-513dbf929b54c229,libcobs-6b1dee9d5bdea72f,libthiserror-39866092b054b09c,libgimli-296da9a8e50f49fd,libstable_deref_trait-03a87de40f153b67,libcpp_demangle-7860fc8072937f8f,librustc_demangle-eb72f1434c999a2e,libcranelift_entity-21b0a26e7871f8be,libcranelift_bitset-30f03b9720f06a49,libtarget_lexicon-c2bd6375b0365d2b,libobject-1f62e4bb9bdfcf6c,libcrc32fast-5811dc940a79c3d7,libwasmparser-0d7d96b4a3efe052,libbitflags-cb13569cd6b97c6f,libsemver-0df01d808a3dc06d,libanyhow-fd7b773a4765faf1,libsp_trie-8e67b1792d574aac,libtrie_root-cd6fccdd6340cdbd,libmemory_db-c5e6dbaf13c26f6b,libsubstrate_prometheus_endpoint-5c12b9a7900d09b8,libhyper_util-5a5cd5b44aec4b70,libtower_service-4a35c7c879daed89,libhttp_body_util-b034e1cb8dd08200,libhyper-95656c8d4f58519a,libwant-f3064d012c3d8066,libtry_lock-4f18628be3bbaced,libhttparse-f4fbd609b213ab40,libh2-30c381f3d58088c5,libindexmap-0b164182d0f31114,libhashbrown-69d519db1601cad7,libfoldhash-0b9d50b2e21e990b,libtokio_util-622d9a83be00716f,libtokio-023e50e7b8f61caa,libsignal_hook_registry-17b0963998dd1c5e,libsocket2-7ff2b403cc9ab9c4,libmio-0b9122e33b758f72,libatomic_waker-73af6e92a6f9ca54,libhttpdate-7d950dda6b89b92e,libhttp_body-9b96f6c6db882063,libhttp-eba3e9adb29bc43c,libprometheus-3132206ee938c463,liblazy_static-8f0b3132db032b6c,libspin-89557400fc372acb,libfnv-6355be18973380fc,libschnellru-f61378d03ee3c3cc,libhashbrown-3919c8818bc67eb3,libahash-fad662209da8ecf3,libgetrandom-e3e91c8775010ef5,libnohash_hasher-6b4cb1f5f42a640e,libtrie_db-cc2b1be7b016992f,libsp_keystore-8c471e435fcb97b0,libsp_arithmetic-1f37f6cd439bac9e,libdocify-1a6de6568abfbcd2,libsp_core-8e69305c26e1fb38,liblibsecp256k1-7e1f72cdb64b9fd8,libbase64-a02c8cb3bef2dd16,liblibsecp256k1_core-f636853577d73283,libdigest-9fe19cea8e21f97b,libfutures-fd178f914b1786b0,libfutures_executor-e471f8cbb5493e7c,libnum_cpus-a089d499910a76de,libfutures_util-1e83564de5be0253,libmemchr-c4a665a7c83181c8,libfutures_io-5c9a7556f82e64ae,libslab-3976d52efe25b86c,libfutures_channel-361f1393442e6b1d,libfutures_sink-4b250c9771a2bac6,libfutures_task-218b0bcc6b4e1621,libpin_utils-cf0786e8d78ab232,libfutures_core-3ae1894eb35020e3,libsubstrate_bip39-3f781c74f2930989,libpbkdf2-6e4e12766b658762,libpassword_hash-d166635faff0baa4,libbase64ct-3ae0299f90296ac6,libhmac-b1120193b5d4219b,libarray_bytes-063d4ca0da8d5687,libbs58-7a0b1dd6106f11fe,libdyn_clone-9f161e920f7ec21f,libbitflags-fb640c373b942643,libtracing-c177af3cd9b7f9f9,libpin_project_lite-9517b556e393a166,libtracing_core-fe0d82b5893977f6,libonce_cell-088dfaabe810f05c,libportable_atomic-c193d425a287f4e4,libthiserror-7d15a1ccb91a03dc,libschnorrkel-d84bf99b9a148171,libmerlin-642993f1839bad45,libgetrandom_or_panic-a14af6e7907a82a9,libed25519_zebra-f15eb5286761cee1,libed25519-5876f4a1b69ef465,libsignature-47b3304c4246685e,libhashbrown-1daa3dee80ffc00f,libfoldhash-52b6f728cd5804eb,libequivalent-170498df83b1c24c,liballocator_api2-ef192bfeedac586f,libcurve25519_dalek-fa8e45b2e1e3c0c1,libsecp256k1-5478ab858dfc8ae0,libsecp256k1_sys-25a32dd497bc2cdc,libsp_externalities-34dc5eb6902cdb8c,libenvironmental-d46df894c447337e,libsp_storage-3370a0074202cbe6,libref_cast-6cc1f74b7ce09c6f,libsp_std-6c1f3c19ff2df05d,libparking_lot-203f1d6c1a2f5d6a,libparking_lot_core-a0e022d63d6a3f94,libsmallvec-f0034f5e656e2895,liblock_api-9d5755e99b3dc9cd,libscopeguard-ec560f87cd1e1afd,libhash_db-2808f669f282810a,libhash256_std_hasher-6cd3d686220c8adc,libprimitive_types-af1255d3d381da7a,libimpl_rlp-3700375fa38ade91,librlp-38db2fa0ccf769a7,libimpl_codec-10a800319d763a5d,libimpl_num_traits-296d69b2e6fab726,libinteger_sqrt-3a57d76cd88cfc6f,libnum_traits-724326b6a4161cbc,libuint-2a9899580f912a58,libcrunchy-a95295e487403c45,libhex-ca165d8c548dda07,libfixed_hash-63be3905af453b3f,librustc_hex-5efafc13c6f47047,libblake2-bf5602bb94ebb6cf,libss58_registry-f1c4bb4fbc681fc8,libnum_format-e3cc4b5791d06296,libitoa-6f50db13f6b9e08f,libsecrecy-a0ced12c09642213,libitertools-06c738f260604af0,libeither-07a3a480f9bf64de,libparity_bip39-47c925e915c1fab6,libunicode_normalization-d4d97d4bca2c03b9,libtinyvec-ee51b41f22a7c11f,libtinyvec_macros-bd057d1890e153d7,libbitcoin_hashes-052e08a5496e3508,libhex_conservative-342127af8c5ca4f5,libsp_crypto_hashing-e04d7c9c81b89c38,libsha2-c05e7209bd6502e9,libcpufeatures-6e9b62d8345c306e,libsha3-fe8954f06f112ff5,libkeccak-9829091b4d1783d2,libtwox_hash-54d76b108df3e1f4,librand-bb05ef44f0f99b62,librand_chacha-0c728b8559a6b5ba,libppv_lite86-7c3995ee204bb988,libzerocopy-b2975503558e03b1,libstatic_assertions-f30b05a76518059f,libblake2b_simd-409e526484a6762d,libconstant_time_eq-ba634f25521f95c3,libarrayref-19431fccf0712618,libdigest-f441201150da6a91,libsubtle-7267faf851c85054,libconst_oid-1fa36c398b425196,libblock_buffer-918b2a4e07a1fa9e,libcrypto_common-4d9408784844dd08,libgeneric_array-635a0a1de7795ef3,libtypenum-8bfc693bcacea3fd,libzeroize-b458a146e61c2bb6,librand_core-bd75ef4c07d154ff,libgetrandom-d35f02d2471bc7fd,liblibc-b44f10b30af41aad,libbyteorder-6d90da58f41ca365,libimpl_serde-b168e22d0a0dab68,libbounded_collections-50bb2cb720100e59,liblog-91b5059d23fce8e0,libjam_codec-be9b36f88a230a6a,libscale_info-8f7564ed91e88a62,libderive_more-2aa0ffbb315dd458,libcfg_if-d06196730a2c709f,libparity_scale_codec-366020d22e5a5b94,libarrayvec-3357df8f8c25dfde,libbytes-095cee7e5476ae65,libbyte_slice_cast-fb5483dcd7f92eb3,libbitvec-acf289c6a997505b,libserde-21e33667da8711ca,libserde_core-34b9c683c6b60b76,libwyz-4662ddbfabbece48,libtap-c7d4206de6d92d5b,libradium-3fd83693e63f8b3a,libfunty-02638f34e69e4b3a,libconst_format-40b72ba4abbb2bdf}.rlib" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib/{libstd-*,libpanic_unwind-*,libobject-*,libmemchr-*,libaddr2line-*,libgimli-*,libcfg_if-*,librustc_demangle-*,libstd_detect-*,libhashbrown-*,librustc_std_workspace_alloc-*,libminiz_oxide-*,libadler2-*,libunwind-*,liblibc-*,librustc_std_workspace_core-*,liballoc-*,libcore-*,libcompiler_builtins-*}.rlib" "-Wl,-Bdynamic" "-lstdc++" "-lstdc++" "-lgcc_s" "-lutil" "-lrt" "-lpthread" "-lm" "-ldl" "-lc" "-L" "/tmp/rustcriVVjV/raw-dylibs" "-B<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/bin/gcc-ld" "-fuse-ld=lld" "-Wl,--eh-frame-hdr" "-Wl,-z,noexecstack" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/secp256k1-sys-4f93b062f00e1d31/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/wasmtime-9b04fcaed6b9cbdc/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/zstd-sys-792dc1b8f18b6dfb/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/blake3-e15c142d04376528/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/secp256k1-sys-5b1b17391b95b067/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/librocksdb-sys-3cc3a72fc4d653f2/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/tikv-jemalloc-sys-20d05c2403dfaec9/out/build/lib" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/lz4-sys-0cf7d07a9f97fbe7/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/ring-85499d409e198c3a/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/libsqlite3-sys-434120d1c0da2b20/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/wasm-opt-cxx-sys-30847dd6066cbafa/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/cxx-026061f434119f42/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/link-cplusplus-07f5fa53e418f2f8/out" "-L" "/home/ubuntu/DePow/blockchain/target/debug/build/wasm-opt-sys-b50fd0c944cfd971/out" "-L" "<sysroot>/lib/rustlib/x86_64-unknown-linux-gnu/lib" "-o" "/home/ubuntu/DePow/blockchain/target/debug/deps/pallet_marketplace-58db12ac33b0e44c" "-Wl,--gc-sections" "-pie" "-Wl,-z,relro,-z,now" "-nodefaultlibs"
  = note: some arguments are omitted. use `--verbose` to show all linker arguments
  = note: collect2: fatal error: ld terminated with signal 9 [Killed]
          compilation terminated.
          

warning: `pallet-marketplace` (lib test) generated 11 warnings (3 duplicates)
error: could not compile `pallet-marketplace` (lib test) due to 1 previous error; 11 warnings emitted
warning: `pallet-solar-farm-management` (lib test) generated 8 warnings (8 duplicates)
warning: `pallet-oracle-integration` (lib test) generated 6 warnings (3 duplicates) (run `cargo fix --lib -p pallet-oracle-integration --tests` to apply 1 suggestion)
warning: `pallet-energy-distribution-nft` (lib test) generated 26 warnings (23 duplicates) (run `cargo fix --lib -p pallet-energy-distribution-nft --tests` to apply 1 suggestion)
warning: `pallet-depow-nft` (lib test) generated 15 warnings (run `cargo fix --lib -p pallet-depow-nft --tests` to apply 3 suggestions)
warning: `depow-node` (bin "depow-node" test) generated 2 warnings (run `cargo fix --bin "depow-node" --tests` to apply 2 suggestions)
```
</details>


