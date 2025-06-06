# MindMint 🧠

AI-Powered On-Chain Memory Vault

MindMint is an innovative application that leverages the power of AI and the security of the Solana blockchain to provide users with a unique and intelligent journaling experience. Securely store your thoughts, memories, and ideas on-chain, and let AI provide you with summaries, mood insights, and connections between your entries.

## 🚀 Features

- **🔒 On-Chain Encrypted Journaling**: Securely store your journal entries on the Solana blockchain. (Encryption to be implemented)
- **🤖 AI Summarization & Insights**: Get concise summaries of your entries and insights into your mood patterns.
- **🔗 Memory Linking**: Discover connections and relationships between different journal entries.
- **💼 Wallet Integration**: Seamlessly connect your Solana wallet to interact with the application.
- **🖼️ NFT Minting (Future)**: Turn significant memories or journal entries into unique NFTs.

## 🛠️ Tech Stack

- **Blockchain**: Solana (using Anchor framework for smart contract development in Rust)
- **Frontend**: React with Next.js (TypeScript) & Tailwind CSS (to be added)
- **AI**: Python microservice using GPT API (via OpenRouter or similar)
- **Deployment**: Vercel (for frontend), and a suitable environment for the AI microservice.

## 📦 Folder Structure

- `.github/workflows/`: GitHub Actions for CI/CD (e.g., Anchor tests).
- `contracts/journal/`: Solana smart contract (Anchor program).
  - `src/lib.rs`: Main contract logic.
  - `Cargo.toml`: Rust dependencies.
- `web/`: React frontend application.
  - `pages/`: Next.js page components.
  - `package.json`: Frontend dependencies.
- `ai/`: Python microservice(s) for AI functionalities.
  - `summarize.py`: Placeholder for summarization logic.
- `assets/`: Logos, UI mockups, demo thumbnails, and other static media.
- `docs/`: Project documentation, pitch, and submission writeups.
- `.gitignore`: Specifies intentionally untracked files that Git should ignore.
- `LICENSE`: Project license file (MIT).
- `README.md`: This file!

## 🔧 Setup Instructions

### Prerequisites
- Node.js (latest LTS version)
- Yarn or npm
- Rust (latest stable version)
- Solana CLI (latest version)
- Anchor CLI (version compatible with contract, e.g., 0.28.0)

### 1. Smart Contracts (`contracts/journal/`)
   ```bash
   # Navigate to the contract directory
   cd mindmint/contracts/journal

   # Install Anchor CLI (if not already installed globally or if you need a specific version)
   # cargo install --git https://github.com/project-serum/anchor anchor-cli --locked --tag v0.28.0
   # (Adjust tag as needed, or install from your own fork if necessary)


   # Build the Anchor program
   anchor build

   # Deploy the program (this will output a program ID, update lib.rs and Anchor.toml)
   # anchor deploy

   # Run tests
   anchor test
   ```
   Remember to replace `"ReplaceWithYourProgramID"` in `lib.rs` and in `Anchor.toml` (create this if it doesn't exist, or it's typically under `programs/devnet/journal = "..."` in `declare_id!`) with your actual program ID after deployment.

### 2. Frontend (`web/`)
   ```bash
   # Navigate to the frontend directory
   cd mindmint/web

   # Install dependencies
   npm install
   # or
   # yarn install

   # Run the development server
   npm run dev
   # or
   # yarn dev
   ```
   The frontend will be accessible at `http://localhost:3000` by default.

### 3. AI Microservice (`ai/`)
   ```bash
   # Navigate to the AI service directory
   cd mindmint/ai

   # It's recommended to use a virtual environment
   python -m venv venv
   source venv/bin/activate # On Windows use `venv\Scripts\activate`

   # Install dependencies (add your AI library dependencies to a requirements.txt file)
   # pip install -r requirements.txt
   # (Create requirements.txt with libraries like Flask, FastAPI, requests, openai, etc.)

   # Run the service (example if using Flask or FastAPI)
   # python summarize.py
   ```
   Ensure your API keys for GPT services are set up correctly as environment variables (e.g., in a `.env` file that is gitignored).

## 🧪 How to Run Locally (Full Stack)

1.  **Start Solana Local Validator**:
    ```bash
    solana-test-validator
    ```
    Keep this running in a separate terminal.
2.  **Deploy Smart Contract**: Follow the steps in "Smart Contracts" setup to build and deploy your contract to the local validator. Note the Program ID.
3.  **Update Program ID**: Ensure your frontend and any other services know the correct Program ID for the deployed contract. This is often stored in a config file or environment variable for the frontend.
4.  **Run AI Service**: Start your Python AI microservice.
5.  **Run Frontend**: Start the Next.js development server.

## 📹 Demo Preview Link

[![Watch the demo](assets/demo-thumb.png)](https://youtu.be/YOUR_VIDEO_LINK)
*(Replace `assets/demo-thumb.png` with your actual thumbnail and `YOUR_VIDEO_LINK` with your demo video URL)*

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure that your code follows the project's linting and testing guidelines.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
