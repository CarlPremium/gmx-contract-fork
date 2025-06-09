# Developer Guide

This repository is a fork of the GMX smart contracts. It uses Hardhat for development.

## Prerequisites
- Node.js v18 or newer
- `npm install` to install dependencies

### Environment
Copy `env.json.sample` to `env.json` and adjust RPC URLs and private keys as needed. The config falls back to the sample file if `env.json` is missing.

### Compilation
Run `npx hardhat compile` to build the contracts. Hardhat downloads the Solidity compiler from the internet. If your environment uses an HTTP proxy or blocks external traffic, the download can fail. Remove `http_proxy` and `https_proxy` variables or configure network access before compiling.

### Tests
Run `npx hardhat test` to execute the test suite. Tests require successful compilation and a working Hardhat environment.

### Troubleshooting
If compilation fails with `HH502` errors, ensure your network connection allows access to `solc-bin`. You may also try setting `HARDHAT_SKIP_COMPILER_DOWNLOAD=false` and running behind a direct internet connection.

### Deployment basics
Deployment scripts live under the `scripts/` folder. They expect token
definitions for the target network in `scripts/core/tokens.js`. Only a handful
of networks are included (BSC, testnet, arbitrumTestnet, arbitrum and avax). Add
your own entry if deploying elsewhere and run for example:

```bash
npx hardhat run scripts/core/deployVault.js --network arbitrumTestnet
```

