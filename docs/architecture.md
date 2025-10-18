# Synth sETH Architecture

## Overview
**Synth sETH (sETH)** is an ERC-20 token representing a synthetic equivalent of Ethereum (ETH) with a fixed supply.  
The contract is fully decentralized — no owner, no minting, and no upgradeability.

It is designed for use within the Ethereum DeFi ecosystem as a liquid, predictable, and secure asset for liquidity pools, collateralization, and derivative protocols.

---

## Smart Contract Design
**Contract:** `SynthSETH.sol`  
**Type:** ERC-20 (Solidity ^0.8.x)  

**Core Characteristics**
- ✅ Fixed total supply (100,000,000 sETH)  
- ✅ No mint or burn functionality  
- ✅ No admin, owner, or proxy  
- ✅ Fully ERC-20 compliant  
- ✅ Safe arithmetic (native Solidity 0.8+ checks)

---

## System Components

| Component | Purpose | Repository Path |
|------------|----------|-----------------|
| `SynthSETH.sol` | Core token logic | `/contracts/SynthSETH.sol` |
| `Uniswap Pool (WETH/sETH)` | Market price discovery pair | `/scripts/deploy/deployLiquidity.js` |
| `Docs` | Technical documentation | `/docs` |
| `Tests` | Core functionality validation | `/tests` |

---

## Flow Diagram
```mermaid
graph TD
    A[User Wallet] -->|Swap| B[Uniswap Pool (WETH/sETH)]
    B -->|Provides Liquidity| C[Synth sETH Contract]
    C -->|Transfers| D[DeFi Protocols (Vaults, Lending, etc.)]
```
