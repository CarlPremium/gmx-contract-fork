# Smart Contract Overview

This project contains the core contracts used by the GMX protocol. They include staking, reward distribution, token contracts and various peripherals.

- **staking** – contracts for reward tracking and vesting
- **oracle** – price feeds and oracles
- **gmx** – core GMX protocol logic

All contracts target Solidity `0.6.12` and are compiled via Hardhat.

For a directory-by-directory list of contracts see
`docs/CONTRACTS_REFERENCE.md`. Instructions for deploying them can be found in
`docs/DEPLOYMENT_GUIDE.md`.

### Security considerations
These contracts are security-critical. Review access control modifiers (e.g. `onlyGov`, `onlyAdmin`) and ensure external calls use appropriate reentrancy guards. Carefully validate arithmetic operations and token transfers.

This repository provides tests under the `test/` directory which can be run with `npx hardhat test` once compilation succeeds.
