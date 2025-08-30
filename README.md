# AntDrop — Web3 Airdrop Platform (BSC / BNB Chain)

AntDrop is a **Web3 airdrop platform** built on the BNB Chain (BSC / BNB Smart Chain).  
Users can connect their wallets, complete tasks, earn points, and join token airdrops.  
The platform also provides a **Token Scanner** (security checks), a **Token Creator** (BEP-20 token deployment), and will include automated distribution via claim contracts in the future.  
Support for **opBNB** and **Greenfield** is planned in upcoming releases.

---

## Features

- **AirdropHub**: Task-based airdrop participation (wallet connect, scoring, duration, participant limits).
- **Token Scanner**:
  - Buy/Sell tax analysis
  - Honeypot detection (sellable or not)
  - Owner privileges (mint, renounce, pause, etc.)
  - Contract verification status via BscScan API
  - Top holder stats & scoring
- **Token Creator**: Deploy BEP-20 tokens on BSC (fee-based with treasury wallet).
- **WalletConnect / Mobile support**: MetaMask, Trust Wallet, SafePal with deep linking.
- **Leaderboard / Points**: Track completed tasks, awards, and scores.
- **Planned**: Claim contract for automated airdrop distribution.

---

## Repository Structure

frontend/ → Vite + React (UI)
backend/ → Node.js + Express (REST API)
contracts/ → Solidity (Hardhat or Foundry)

---

## Quick Start

### Requirements
- Node.js 18+
- NPM / PNPM / Yarn
- Hardhat or Foundry for smart contracts
- BscScan API key (optional, for contract verification)
- Moralis or other Web3 Data API key (optional, for holders)

### 1) Frontend

```bash
cd frontend
npm install
cp .env.example .env
npm run dev
npm run build

### 2) Backend

```bash
cd backend
npm install
cp .env.example .env
npm run dev     # or node server.js

### 3) Contracts (Hardhat example)

```bash
cd contracts
npm install
cp .env.example .env
npx hardhat compile
npx hardhat test
npx hardhat run scripts/deploy.js --network bscTestnet
