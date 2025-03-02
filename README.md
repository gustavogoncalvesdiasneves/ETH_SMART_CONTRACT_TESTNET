# PG4 Coin - Ethereum Testnet Token

## Overview
PG4 Coin is an ERC-20 compatible token developed in Solidity for Ethereum testnet environments. It is designed for testing purposes and allows developers and testers to simulate token transactions on a local blockchain environment.

## Features
- Implements the ERC-20 standard interface.
- Supports token transfers, approvals, and allowances.
- Uses `Ganache` for local blockchain simulation and wallet balance management.
- `MetaMask` is used to manage Ganache accounts and sign transactions.
- Developed and deployed using `Remix IDE`.
- Includes a test faucet mechanism to distribute tokens during development.

## Tech Stack
- **Solidity (0.8.x)** - Smart contract programming language.
- **Remix IDE** - Web-based development environment for smart contracts.
- **Ganache** - Personal blockchain for Ethereum development.
- **MetaMask** - Ethereum wallet and browser extension for managing accounts and signing transactions.

## Contract Details
- **Token Name**: PG4 Coin
- **Symbol**: PG4
- **Decimals**: 18
- **Total Supply**: 10 PG4 (scaled to 18 decimals)

## Deployment Steps
1. **Start Ganache** to create a local Ethereum blockchain for testing:
   ```sh
   ganache --gasLimit 10000000
   ```
2. **Configure MetaMask** to connect to Ganache:
   - Open MetaMask.
   - Add a custom network with the RPC URL `http://127.0.0.1:8545`.
   - Import one of the generated accounts from Ganache.
3. **Compile and Deploy using Remix**:
   - Open [Remix IDE](https://remix.ethereum.org/).
   - Create a new Solidity file and paste the PG4Coin contract.
   - Compile the contract.
   - Deploy the contract using the `Injected Web3` environment (connected to MetaMask with Ganache).

## Token Functionality
### 1. Total Supply
```solidity
function totalSupply() public view override returns (uint256);
```
Returns the total supply of PG4 tokens.

### 2. Balance Of
```solidity
function balanceOf(address tokenOwner) public view override returns (uint256);
```
Checks the balance of a given address.

### 3. Transfer
```solidity
function transfer(address receiver, uint256 numTokens) public override returns (bool);
```
Transfers tokens from the sender to a recipient.

### 4. Approve
```solidity
function approve(address delegate, uint256 numTokens) public override returns (bool);
```
Approves another address to spend tokens on behalf of the sender.

### 5. Allowance
```solidity
function allowance(address owner, address delegate) public view override returns (uint256);
```
Returns the amount of tokens that a delegate is allowed to spend on behalf of the owner.

### 6. Transfer From
```solidity
function transferFrom(address owner, address buyer, uint256 numTokens) public override returns (bool);
```
Transfers tokens from one account to another using an approved allowance.

## Testing with Ganache & MetaMask
- After deploying the contract, use **Ganache's test accounts** to simulate token transfers.
- Add the deployed PG4 token contract to MetaMask using the contract address.
- Use MetaMask to send and receive PG4 tokens between test accounts.

## License
This project is licensed under the **GPL-3.0** License.

