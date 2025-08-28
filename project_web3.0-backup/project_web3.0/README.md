# Krypt - Web 3.0 Blockchain Application
![Krypt](https://i.ibb.co/DVF4tNW/image.png)

Web3.0 Base DApp

This is a base decentralized application (DApp) built with Solidity, Hardhat, and React (Vite + Tailwind).
Currently, it allows users to connect their wallet (MetaMask), send ETH transactions, and view a history of past transfers.

⚡️ Planned Extension:
This base will be extended into a decentralized voting system. Each user will have a unique key generated from their fingerprint which will act as their identity. This key will be required to cast votes (transactions) securely and uniquely on the blockchain.

🚀 Features

Connect with MetaMask wallet

Send and log ETH transactions on blockchain

Store transaction details (sender, receiver, message, keyword, timestamp) in smart contract

React + Tailwind frontend with reusable components

Global state management with Context API + Ethers.js

Dummy data included for testing UI

📂 Project Structure
project_web3.0-main/
├─ client/                  # React + Vite frontend
│  ├─ index.html            # Root HTML file
│  ├─ package.json          # Frontend dependencies & scripts
│  ├─ src/
│  │  ├─ App.jsx            # Main app layout
│  │  ├─ main.jsx           # React entry, wraps in Tx Provider
│  │  ├─ components/        # UI parts (Navbar, Welcome, Services, etc.)
│  │  ├─ context/           # TransactionContext (ethers.js logic)
│  │  └─ utils/             # ABI, contract constants, helpers
│
└─ smart_contract/          # Solidity + Hardhat workspace
   ├─ contracts/            # Core smart contract
   │   └─ Transactions.sol  # Logs & stores transactions
   ├─ scripts/              # Deployment script
   ├─ hardhat.config.js     # Hardhat setup
   └─ test/                 # Contract test samples

⚙️ Smart Contract

File: smart_contract/contracts/Transactions.sol

Defines a Transaction struct

Saves transfers in an array

Emits an event for every transaction

Provides functions:

addToBlockchain(address receiver, uint amount, string message, string keyword)

getAllTransactions()

getTransactionCount()

🖥️ Frontend

React (Vite) + Tailwind → fast dev server & styled UI

TransactionContext.jsx → connects to Ethereum, uses ethers.js, wraps app with provider

Welcome.jsx → wallet connect + send transaction form

Transactions.jsx → displays all past transactions

Services.jsx, Navbar.jsx, Footer.jsx, Loader.jsx → UI sections

🔑 How It Works

User connects MetaMask wallet from the frontend

User fills receiver, amount, message → sends transaction

Smart contract logs transaction + emits event

Frontend fetches all past transactions and shows in UI

🛠️ Getting Started
Prerequisites

Node.js v16+

MetaMask browser extension

Setup

Clone repository

git clone https://github.com/your-username/project_web3.0.git
cd project_web3.0-main


Install dependencies

cd smart_contract
npm install

cd ../client
npm install


Compile and deploy contract (using Sepolia testnet)

cd smart_contract
npx hardhat compile
npx hardhat run scripts/deploy.js --network sepolia


Copy deployed contract address → paste into
client/src/utils/constants.js

Start frontend

cd ../client
npm run dev


Open in browser at http://localhost:5173

🌐 Connect to Test Network

Open MetaMask → Settings → Advanced → Enable Test Networks

Switch to Sepolia Test Network

Get free test ETH from Sepolia faucet

Send transactions using the DApp

📌 Future Work

Extend into a voting DApp

Each user will be assigned a unique key generated via fingerprint

This key will act as the identity and authorization for transactions (votes)

Transactions will represent votes, stored immutably on-chain

📝 License

MIT