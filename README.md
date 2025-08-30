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

yaml
Kodu kopyala

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
2) Backend
bash
Kodu kopyala
cd backend
npm install
cp .env.example .env
npm run dev     # or node server.js
3) Contracts (Hardhat example)
bash
Kodu kopyala
cd contracts
npm install
cp .env.example .env
npx hardhat compile
npx hardhat test
npx hardhat run scripts/deploy.js --network bscTestnet
Configuration
Frontend .env.example
bash
Kodu kopyala
VITE_API_URL=http://localhost:3001
VITE_BSC_CHAIN_ID=0x61   # 0x38 mainnet, 0x61 testnet
VITE_WALLETCONNECT_PROJECT_ID=your_wc_project_id
Backend .env.example
bash
Kodu kopyala
PORT=3001
CORS_ORIGINS=http://localhost:5173,https://antdrop.io,https://www.antdrop.io
DB_CLIENT=sqlite
DB_URL=./antdrop.db
BSCSCAN_API_KEY=your_bscscan_key
MORALIS_API_KEY=optional
AIRDROP_DURATION_DAYS=7
AIRDROP_PARTICIPANT_CAP=5000
Contracts .env.example
bash
Kodu kopyala
PRIVATE_KEY=0xabc...
BSC_RPC=https://bsc-dataseed.binance.org
BSCSCAN_API_KEY=your_bscscan_key
