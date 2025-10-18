# Synth sETH Integration Guide

## Purpose
To show how to use the token in practice — via code, DeFi pools, wallets, and third-party protocols.  
This document is intended for **developer integrators and users** who want to interact with the token via code, wallets, or DeFi applications.

---

## 1. Overview
The token is fully **ERC-20 compatible** and suitable for DeFi.  

**Typical use cases:**  
- **DEXs** (Decentralized Exchanges)

> Future integrations such as lending, yield farming, or bridges may be added as the ecosystem develops.

---

## 2. Ethers.js Usage Examples

### Connect to the contract
```js
import { ethers } from "ethers";

// Example provider (Infura, Alchemy, etc.)
const provider = new ethers.JsonRpcProvider("https://mainnet.infura.io/v3/YOUR_PROJECT_ID");
const signer = provider.getSigner();

// ABI should be generated from the contract source code or obtained from Etherscan
const abi = [ /* ABI here */ ];

const sETH = new ethers.Contract(
  "0xF119ADa773624761108A12bc20503B2195727061",
  abi,
  signer
);
Get token balance
js
const balance = await sETH.balanceOf("0xYourWallet");
console.log("Balance:", ethers.formatUnits(balance, 18));
Transfer tokens
js
const tx = await sETH.connect(signer).transfer(
  "0xRecipient",
  ethers.parseUnits("10", 18)
);
await tx.wait();
console.log("Sent 10 sETH");

3. Integration Use Cases
Integration	Example
DEX	Create a WETH/sETH pool on Uniswap

Other integrations such as lending, yield farming, and bridges may be added in the future.

4. ABI Reference
The full ABI can be generated from the contract source code or obtained from the verified contract on Etherscan:

Contract Address: 0xF119ADa773624761108A12bc20503B2195727061

The ABI is required to interact with the contract using scripts, wallets, or other applications.

5. Post-Deployment Actions
Add the token to MetaMask (Add Token → Custom → Contract Address)

Create a WETH/sETH pool on Uniswap

Optionally, lock or manage initial liquidity via a trusted service (e.g., Team Finance or Unicrypt)

🧩 Summary
File	Purpose	Audience	Example Contents
/docs/architecture.md	How the token is structured (internal architecture and design)	Auditors, DevOps	Contract logic, flow diagram, design philosophy
/docs/integration.md	How to use the token (integration and code examples)	Developers, DeFi partners	JS examples, MetaMask, Uniswap, ABI
