

# Build Your First dApp in Under 20 Minutes 🚀

Welcome to the repository for building your first decentralized application (dApp) in under 20 minutes! This project is designed for beginners in blockchain development and walks you through deploying your first smart contract and integrating it with a simple front-end application.

---

## 📖 Overview

In this repository, you will:
- Set up essential blockchain development tools.
- Deploy a simple smart contract on a local Ethereum blockchain using [Ganache](https://trufflesuite.com/ganache/).
- Interact with the deployed contract through a basic HTML/JavaScript front-end.
- Learn the basics of connecting your dApp to the blockchain using [web3.js](https://web3js.readthedocs.io/).

This project assumes a basic understanding of blockchain concepts, Ethereum, and JavaScript. If you're completely new, check out the [blog post](#) for detailed guidance.

---

## 🛠 Prerequisites

Before starting, make sure you have the following tools installed on your system:
1. **[Git](https://git-scm.com/)** - For cloning repositories.
2. **[MetaMask](https://metamask.io/)** - A browser extension for managing your Ethereum accounts.
3. **[Ganache](https://trufflesuite.com/ganache/)** - A local Ethereum blockchain for testing and development.
4. **[Remix IDE](https://remix.ethereum.org/)** - An online IDE for compiling and deploying smart contracts.
5. **Code Editor** - Any IDE supporting HTML, CSS, and JavaScript (e.g., [VS Code](https://code.visualstudio.com/)).

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone <repository-url>
cd <repository-folder>
```

### 2. Install and Configure MetaMask
1. Install MetaMask as a browser extension.
2. Securely store your recovery phrase.
3. Connect MetaMask to the Ganache local blockchain:
   - Add a custom network using `http://127.0.0.1:7545` (RPC URL) and `5777` (Chain ID).

### 3. Start Ganache
- Launch Ganache on your local machine to simulate an Ethereum blockchain.
- Use the default RPC Server: `http://127.0.0.1:7545`.

### 4. Deploy the Smart Contract
1. Open [Remix IDE](https://remix.ethereum.org/).
2. Copy the code from `Contracts/Election.sol` in this repository into a new Solidity file in Remix.
3. Compile the contract using Solidity compiler version `0.4.2`.
4. Deploy the contract:
   - Use **Custom - External HTTP Provider** as the environment.
   - Connect to the Ganache RPC server (`http://127.0.0.1:7545`).
5. Copy the deployed contract address and ABI for the next steps.

### 5. Configure the Frontend
1. Open `index.html` in a code editor.
2. Replace the following placeholders in the `<script>` section:
   - `var contractAbi = [];` → Add the contract ABI.
   - `var contractAddress = '';` → Add the contract address.
3. Save the file.

### 6. Run the Frontend
Open `index.html` in your preferred web browser to interact with your deployed contract. You can:
- View the current candidate name.
- Set a new candidate name.

---

## 📂 Project Structure
```
.
├── Contracts/
│   └── Election.sol      # Solidity smart contract
├── index.html            # Frontend HTML file
├── styles.css            # Optional CSS for styling
└── README.md             # Project documentation
```

---

## 🌟 Features
- Deploy a simple Election contract on a local blockchain.
- Connect the contract to a front-end application using web3.js.
- Interact with the blockchain through a browser-based dApp.

---

## 🤝 Acknowledgments
Inspired by the Dapp University YouTube tutorial. Check out their [video](https://www.youtube.com/watch?v=KkZ6iYnSDRw) for additional insights.

---

## 💡 Contributing
Feel free to submit issues or pull requests to improve this project. Contributions are welcome!

---

## 📢 Stay Connected
- [Blog Post](https://rafsunsheikh116.medium.com/new-to-blockchain-development-build-your-first-dapps-in-under-20-minutes-1f2f392d50fe) — Full tutorial with screenshots and explanations.
- [Medium Profile](https://medium.com/@rafsunsheikh116) — More articles on blockchain and technology.
- [LinkedIn](https://www.linkedin.com/in/mdrafsunsheikh/) — Connect with me for updates.
- [Website](rafsunsheikh.github.io) — Find details about my works.

If you found this repository helpful, please give it a ⭐ and share it with others! Your support keeps me motivated to create more tutorials. ❤️