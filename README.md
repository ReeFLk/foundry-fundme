# Foundry Fund Me

This repository is a part of the Cyfrin Solidity Course, specifically focusing on Foundry Fund Me.

## Table of Contents

- [Foundry Fund Me](#foundry-fund-me)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Requirements](#requirements)
    - [Quickstart](#quickstart)
  - [Usage](#usage)
    - [Deploy](#deploy)
    - [Testing](#testing)
      - [Test Coverage](#test-coverage)
  - [Deployment to a Testnet or Mainnet](#deployment-to-a-testnet-or-mainnet)
  - [Scripts](#scripts)
    - [Withdraw](#withdraw)
    - [Estimate Gas](#estimate-gas)
  - [Formatting](#formatting)
  - [Thank you!](#thank-you)

## Getting Started

### Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - Verify by running `git --version`
- [foundry](https://getfoundry.sh/)
  - Verify by running `forge --version`

### Quickstart

```bash
git clone https://github.com/Cyfrin/foundry-fund-me-f23
cd foundry-fund-me-f23
forge build
```

## Usage

### Deploy

```bash
forge script script/DeployFundMe.s.sol
```

### Testing

This repository covers Unit and Forked test tiers.

```bash
forge test
```

or

```bash
forge test --match-test testFunctionName
```

or

```bash
forge test --fork-url $SEPOLIA_RPC_URL
```

#### Test Coverage

```bash
forge coverage
```

## Deployment to a Testnet or Mainnet

1. **Setup Environment Variables**

   Set `SEPOLIA_RPC_URL` and `PRIVATE_KEY` as environment variables, similar to `.env.example`. Optionally, add `ETHERSCAN_API_KEY` for Etherscan verification.

2. **Get Testnet ETH**

   Visit [faucets.chain.link](https://faucets.chain.link/) to obtain testnet ETH.

3. **Deploy**

```bash
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

## Scripts

After deploying to a testnet or local net, you can run the scripts.

For locally deployed contracts:

```bash
cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

or

```bash
forge script script/Interactions.s.sol --rpc-url sepolia --private-key $PRIVATE_KEY --broadcast
```

### Withdraw

```bash
cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()" --private-key <PRIVATE_KEY>
```

### Estimate Gas

Estimate gas costs by running:

```bash
forge snapshot
```

And find the output file named `.gas-snapshot`

## Formatting

Run code formatting:

```bash
forge fmt
```

## Thank you!

If you found this helpful, consider following or donating to Cyfrin!

- ETH/Arbitrum/Optimism/Polygon/etc Address: 0x9680201d9c93d65a3603d2088d125e955c73BD65
