# ERC20 Token Deployment and Etherscan Verification

This guide walks you through creating, deploying, and verifying an ERC20 token on Etherscan using **Remix** and **OpenZeppelin**.

---

## Prerequisites

- **MetaMask** wallet installed and configured.
- Testnet funds (e.g., Goerli or Sepolia).  
  - [Get testnet funds here](https://faucet.paradigm.xyz/).
- A verified Etherscan account with an API key.  
  - [Sign up for Etherscan](https://etherscan.io/).

---

## Steps to Create and Deploy the Token

### 1. Open Remix
- Visit [Remix IDE](https://remix.ethereum.org).
- Create a new **workspace** from the upper-left menu.

### 2. Use OpenZeppelin ERC20 Template
- Add the OpenZeppelin Contracts library:
  - Run the following in the Remix terminal:  
    ```bash
    npm install @openzeppelin/contracts
    ```
- Create a new Solidity file, e.g., `MyToken.sol`.
- Add the following code:
  ```solidity
  // SPDX-License-Identifier: MIT
  pragma solidity ^0.8.0;

  import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

  contract MyToken is ERC20 {
      constructor(string memory name, string memory symbol) ERC20(name, symbol) {
          _mint(msg.sender, 1000 * 10 ** decimals());
      }
  }

Modify the name, symbol, and initial supply in the constructor as needed.
### 3. Compile the Contract
Click the Solidity compiler logo in Remix (on the left).
Select MyToken.sol and compile the contract.
### 4. Deploy the Contract
Click the Deploy & Run Transactions logo (Ethereum icon) in Remix.
In the Environment dropdown, select Injected Provider - MetaMask.
Connect your wallet (ensure it has testnet funds).
Select the MyToken contract from the dropdown.
Deploy the contract and confirm the transaction in MetaMask.
Steps to Verify the Contract on Etherscan
1. Install Etherscan Plugin in Remix
In Remix, click the Plugins icon (bottom-left).
Search for Etherscan and install it.
2. Retrieve Contract Details
After deployment, copy the contract address from the Remix output console.
Save the contract address for later use.
3. Verify the Contract
Navigate to the Etherscan Plugin in Remix.
Enter the following details:
Contract Address: The address from the deployment step.
Contract Name: MyToken.
Compiler Version: Match the Solidity compiler version used in Remix.
Etherscan API Key: Your API key from Etherscan.
Click Verify.
Interacting with the Token on Etherscan

Once verified, you can:

Mint tokens (if enabled in your contract).

Transfer tokens.

View token details (name, symbol, supply, etc.).

Additional Resources

OpenZeppelin Documentation

Remix Documentation

Etherscan API Guide
