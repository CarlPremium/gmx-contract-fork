# Contract Reference

This reference briefly describes the purpose of each contract in the repository. Contracts are grouped by directory.

## `access`
- **Governable** – base contract providing a `gov` address that can perform administrative actions.
- **TokenManager** – manages a list of tokens and has the ability to mint/burn them.

## `amm`
- **PancakeFactory**, **PancakePair**, **PancakeRouter** – fork of Uniswap-style automated market maker for swaps.
- **UniFactory**, **UniPool**, **UniNftManager** – minimal Uniswap V3-style components used for internal liquidity management.

## `core`
- **Vault** – central contract that holds assets and manages leveraged positions.
- **Router** – main entry point for swaps and position adjustments.
- **PositionManager**, **PositionRouter**, **BasePositionManager** – helpers that create and manage position orders.
- **OrderBook** – stores swap/position orders for execution.
- **ShortsTracker** – tracks global short positions.
- **VaultErrorController**, **VaultUtils** – utility contracts for the vault.

## `gmx`
- **GMX**, **EsGMX**, **GLP** – token contracts for the GMX ecosystem.
- **GmxMigrator**, **GmxIou**, **GmxFloor** – helper contracts for migrations and IOU handling.

## `gambit-token`
- **GMT** – Gambit token implementation.
- **Treasury** – simple treasury for GMT funds.

## `oracle`
- **PriceFeed** – provides price data to the protocol.
- **FastPriceFeed**, **FastPriceEvents** – oracle system for fast price updates.

## `peripherals`
- **Timelock**, **GmxTimelock**, **PriceFeedTimelock** – administrative timelocks.
- **Reader**, **RewardReader**, **OrderBookReader** – view helpers that aggregate protocol data.
- **BalanceUpdater**, **BatchSender**, **EsGmxBatchSender** – utility contracts for batch operations.

## `referrals`
- **ReferralStorage** – records referral relationships and discounts.
- **ReferralReader** – view contract to read referral info.

## `staking`
- **RewardRouterV2**, **RewardRouter** – handle staking and unstaking for GMX and GLP.
- **RewardTracker**, **RewardDistributor** – track rewards and distribute them over time.
- **Vester** – contract for vesting esGMX to GMX.
- **StakedGlp**, **StakedGlpMigrator** – GLP staking helpers.
- **BonusDistributor**, **StakeManager**, **GlpBalance** – additional staking utilities.

Interfaces are located under each directory's `interfaces` folder.

