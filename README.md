# Ethereum Auction Smart Contract

[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg)](https://opensource.org/licenses/GPL-3.0)

This repository contains a simple Ethereum smart contract for conducting auctions on the Ethereum blockchain.

## Smart Contract Overview

### Auction Contract

The `Auction` contract facilitates the creation and management of auctions on the Ethereum blockchain. The key features include:

- **Auction Parameters:**
  - `owner`: The Ethereum address of the auction owner.
  - `startBlock` and `endBlock`: Blocks defining the start and end of the auction.
  - `ipfsHash`: An IPFS hash that can be used to store additional information off-chain.
  - `auctionState`: An enumeration representing the current state of the auction (Started, Running, Ended, Canceled).
  - `highestBindingBid`: The highest bid at the moment, binding for the auction winner.
  - `highestBidder`: The Ethereum address of the highest bidder.
  - `bids`: A mapping from bidder addresses to their respective bids.
  - `bidIncrement`: The increment value for each bid.
  - `ownerFinalized`: A boolean indicating whether the owner has already finalized the auction.

### Functionality

- **Auction Initialization:**
  - The auction is initialized with the owner's address, a running state, and defined start and end blocks.

- **Bid Placement:**
  - Participants (non-owners) can place bids during the auction's running period.
  - Bids must be greater than the current highest bid.
  - The highest bidder and binding bid are updated accordingly.

- **Auction Finalization:**
  - The owner can cancel the auction before it ends.
  - The owner or a bidder can finalize the auction after it has ended or been canceled.
  - Funds are distributed to the appropriate parties (winner or canceled auction participants).
  - The owner can only finalize the auction and receive the highestBindingBid once.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) and npm installed
- [Truffle](https://www.trufflesuite.com/truffle) installed globally (`npm install -g truffle`)
- Ethereum development environment (e.g., [Ganache](https://www.trufflesuite.com/ganache))

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/itsmohitnarayan/AuctionSmartcontract.git
   cd auction-smart-contract
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

## Usage

1. Start your Ethereum development environment (e.g., Ganache).
2. Compile the smart contracts:
   ```bash
   truffle compile
   ```
3. Migrate the contracts to the blockchain:
   ```bash
   truffle migrate
   ```
4. Run tests:
   ```bash
   truffle test
   ```
5. Interact with the contracts using the provided scripts or integrate them into your DApp.

## Contributing

Contributions are welcome! Please read the [Contributing Guidelines](CONTRIBUTING.md) for details on how to contribute to this project.

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE). See the [LICENSE](LICENSE) file for details.
