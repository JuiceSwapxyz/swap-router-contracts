# JuiceSwap Swap Router

[![Tests](https://github.com/JuiceSwapXyz/swap-router-contracts/workflows/Tests/badge.svg)](https://github.com/JuiceSwapXyz/swap-router-contracts/actions?query=workflow%3ATests)
[![Lint](https://github.com/JuiceSwapXyz/swap-router-contracts/workflows/Lint/badge.svg)](https://github.com/JuiceSwapXyz/swap-router-contracts/actions?query=workflow%3ALint)

Smart contracts for swapping on the JuiceSwap V3 protocol.

JuiceSwap is a fork of Uniswap V3 with custom modifications including a 50% maximum protocol fee cap (governance-controlled).

## Installation

```bash
npm install @juiceswapxyz/swap-router-contracts
```

or

```bash
yarn add @juiceswapxyz/swap-router-contracts
```

## Local Deployment

To deploy this code to a local testnet, import bytecode from the npm package artifacts:

```typescript
import {
  abi as SWAP_ROUTER_ABI,
  bytecode as SWAP_ROUTER_BYTECODE,
} from '@juiceswapxyz/swap-router-contracts/artifacts/contracts/SwapRouter02.sol/SwapRouter02.json'

// deploy the bytecode
```

This ensures you are testing against the same bytecode deployed to mainnet and public testnets.

## Using Solidity Interfaces

Import swap router contract interfaces into your Solidity smart contracts:

```solidity
import '@juiceswapxyz/swap-router-contracts/contracts/interfaces/ISwapRouter02.sol';

contract MyContract {
  ISwapRouter02 router;

  function doSomethingWithSwapRouter() {
    // router.exactInput(...);
  }
}
```

## Development

### Install Dependencies

```bash
yarn install
```

### Compile Contracts

```bash
yarn compile
```

### Run Tests

Some tests use Hardhat mainnet forking and require an archive node. Create a `.env` file in the workspace root:

```
ARCHIVE_RPC_URL='...'
```

Or set the variable when running tests:

```bash
export ARCHIVE_RPC_URL='...' && yarn test
```

## License

GPL-2.0-or-later
