## Hi there 👋

# Shamecoin

**Shamecoin** is a Solana-based token and dApp that transforms personal shame into gamified self-improvement. Individuals publicly confess their biggest challenges, gather community votes, and prove real progress on a live broadcast showdown—while an AI agent sniffs out deception. If they’re legit, they receive a reward of Shamecoin tokens; if not, the airdrop rolls over to the next round.

---

## Table of Contents

1. [Overview](#overview)
2. [Architecture](#architecture)
3. [Getting Started](#getting-started)
4. [Smart Contracts](#smart-contracts)
5. [Frontend dApp](#frontend-dapp)
6. [AI Integration](#ai-integration)
7. [Contributing](#contributing)
8. [License](#license)

---

## Overview

- **Name**: Shamecoin (SHM)
- **Blockchain**: Solana
- **Concept**:
  1. **Shamegames**: Users post their “shames” and vow to fix them.
  2. **Community Voting**: The crowd upvotes compelling posts.
  3. **Proof-of-Change**: Winners must prove genuine progress in a 1-month window.
  4. **Final Showdown**: A live broadcast Q&A against an AI lie-detector.
  5. **Airdrop or Rollover**: If the crowd is convinced, tokens are airdropped; otherwise, they roll over to the next round.

---

## Architecture

We split the project into three main components:

1. **Smart Contract (Solana Program)**:
   - Built with the [Anchor framework](https://github.com/coral-xyz/anchor).
   - Manages creation of shame posts, voting logic, proof submissions, and token airdrops.

2. **Frontend dApp**:
   - Developed in React (TypeScript) with [@solana/wallet-adapter](https://github.com/solana-labs/wallet-adapter) for wallet connections.
   - Displays real-time data from the on-chain program, handles upvoting, and supports user proof submissions via IPFS/Arweave.

3. **AI Service** (optional advanced feature):
   - Python microservice using NLP or image classification to detect spam, hateful content, or possible fraud (in the live broadcast phase).
   - Could incorporate OpenAI or Hugging Face models for text and image moderation.

For a deeper look, see [docs/architecture.md](./docs/architecture.md).

---

## Getting Started

### Prerequisites

- [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
- [Node.js](https://nodejs.org/en/) (v14+ recommended)
- [Yarn](https://classic.yarnpkg.com/en/docs/install) or npm
- [Rust](https://www.rust-lang.org/tools/install)
- [Anchor CLI](https://project-serum.github.io/anchor/getting-started/installation.html)

### Local Environment Setup

```bash
# Clone the repo
git clone https://github.com/YOUR-USERNAME/shamecoin.git
cd shamecoin

# Install dependencies for smart-contract
cd smart-contract
anchor build # or anchor test

# Install dependencies for frontend
cd ../frontend
yarn install
yarn start

# For AI Service (if using Python-based scripts):
cd ../ai-service
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python main.py
