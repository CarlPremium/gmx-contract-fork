# Deployment Guide

This guide explains how to deploy the GMX contracts using Hardhat and interact with the protocol after deployment.

## 1. Setup
1. Copy `env.json.sample` to `env.json` and update RPC URLs and private keys.
2. Install dependencies with `npm install`.

### Token configuration
Deployment scripts rely on token lists defined in `scripts/core/tokens.js`.
Only the `bsc`, `testnet`, `arbitrumTestnet`, `arbitrum` and `avax` networks
are provided out of the box. If you plan to deploy to a different network such
as Goerli, add a matching entry in this file with the token addresses you want
to use. Running a script on an undefined network will now result in a clear
error message.

## 2. Compile
Run `npx hardhat compile` to build the Solidity contracts. Ensure your environment has internet access so Hardhat can download `solc`.

## 3. Deploy
Each subsystem has a deploy script in `scripts/`. For example, to deploy the core vault contracts:

```bash
npx hardhat run scripts/core/deployVault.js --network arbitrumTestnet
```
Replace `arbitrumTestnet` with whichever network key you have configured in the
`tokens.js` file.

Deployment scripts log the address of each contract after the transaction is mined. The helper function `deployContract` prints a line similar to:

```
Deploying Vault ...
... Completed deployment of Vault at 0xabc123...
```

All addresses for the current network are also written to `.tmp-addresses-<network>.json` for convenience.

## 4. Using the Contracts
After deployment you can interact with the contracts using Hardhat tasks, scripts or a frontend. Some common interactions:

- Approve tokens to the `Router` then call `Router.swap` for token swaps.
- Use `PositionRouter.createIncreasePosition` to open leveraged positions via the `Vault`.
- Stake tokens through `RewardRouterV2` to earn rewards.

Refer to `docs/CONTRACTS_REFERENCE.md` for a list of contracts and their purpose.

