# Synth sETH Integration Guide

## Purpose
To show how to use the token in practice — via code, DeFi pools, wallets, and third-party protocols.  
This document is intended for **developer integrators and users** who want to interact with the token via code, wallets, or DeFi applications.

---

## 1. Overview
The token is fully **ERC-20 compatible** and suitable for DeFi.  

**Typical use cases:**  
- DEXs  
- Lending  
- Yield farming  
- Bridges  

---

## 2. Ethers.js Usage Examples

### Connect to the contract
```js
import { ethers } from "ethers";

const sETH = new ethers.Contract(
  "0xYourContract",
  abi,
  provider
);
```
## Get token balance
```
const balance = await sETH.balanceOf("0xYourWallet");
console.log("Balance:", ethers.formatUnits(balance, 18));
```
## Transfer tokens
```
const tx = await sETH.connect(signer).transfer("0xRecipient", ethers.parseUnits("10", 18));
await tx.wait();
console.log("Sent 10 sETH");
```
## Integration Use Cases
```
| Integration | Example |
|-------------|---------|
| DEX | Create a WETH/sETH pool on Uniswap |
```
## ABI Reference

The full ABI can be generated from the contract source code or obtained from the verified contract on Etherscan:

- Contract Address: [0xF119ADa773624761108A12bc20503B2195727061](https://etherscan.io/address/0xF119ADa773624761108A12bc20503B2195727061)



