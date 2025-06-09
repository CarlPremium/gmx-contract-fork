# GMX Contracts
Contracts for GMX.

Docs at https://gmxio.gitbook.io/gmx/contracts.

## Install Dependencies
If npx is not installed yet:
`npm install -g npx`

Install packages:
`npm i`

### Environment configuration
Copy `env.json.sample` to `env.json` and update any network URLs or keys as needed for local development. The sample values point to a local Hardhat node and use a dummy private key. `env.json` is ignored by git so your keys remain private.

### Build prerequisites
Use a recent LTS version of Node.js (v18 or newer is recommended). If your environment uses an HTTP proxy, Hardhat may fail to download compilers. Removing the `http_proxy` and `https_proxy` variables fixes the issue.

## Compile Contracts
Run `npm install` once to install dependencies and then execute:
```
npx hardhat compile
```
The configuration will fall back to `env.json.sample` if `env.json` is missing.

## Run Tests
`npx hardhat test`


See `docs/DEVELOPER_GUIDE.md` for development notes.
Additional documentation can be found in `docs/SMART_CONTRACT_OVERVIEW.md`.
Deployment instructions live in `docs/DEPLOYMENT_GUIDE.md` and a
full list of contracts is provided in `docs/CONTRACTS_REFERENCE.md`.
