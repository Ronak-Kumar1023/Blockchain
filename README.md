# Blockchain Project

This project implements a basic blockchain and a simple cryptocurrency using Python. The blockchain is managed by a Flask web application that allows nodes to interact with the blockchain, mine new blocks, and maintain consensus across a distributed network.

## Features

- **Blockchain Structure**: The project creates a chain of blocks, where each block contains a list of transactions, a proof of work, and a hash of the previous block.
- **Proof of Work**: Implements a simple Proof of Work algorithm to secure the blockchain.
- **Transaction Handling**: Allows for new transactions to be added, which are then included in the next mined block.
- **Consensus Mechanism**: Ensures that the longest valid chain is adopted by all nodes in the network, maintaining consistency across the distributed blockchain.
- **RESTful API**: Provides a set of endpoints to interact with the blockchain, including mining new blocks, adding transactions, registering new nodes, and resolving conflicts.

## Installation

1. **Clone the repository:**

```bash
git clone https://github.com/yourusername/blockchain-project.git
cd blockchain-project
```

2. **Install dependencies:**

```bash
pip install Flask requests
```

3. **Run the application:**

Start the Flask application:
```bash
python blockchain.py
```

The application will run on http://0.0.0.0:5001.

## API Endpoints
- Mine a new block: GET /mine
- Create a new transaction: POST /transactions/new
- Get the full blockchain: GET /chain
- Register new nodes: POST /nodes/register
- Resolve conflicts: GET /nodes/resolve

## Example Requests
Mining a block:

```bash
curl http://localhost:5001/mine
```

Creating a transaction:

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "sender": "address1",
  "recipient": "address2",
  "amount": 50
}' http://localhost:5001/transactions/new
```


Viewing the full chain:

```bash
curl http://localhost:5001/chain
```

Registering new nodes:

```bash
curl -X POST -H "Content-Type: application/json" -d '{
  "nodes": ["http://localhost:5002", "http://localhost:5003"]
}' http://localhost:5001/nodes/register
```

Resolving conflicts:

```bash
curl http://localhost:5001/nodes/resolve
```

## How It Works
- Genesis Block: The blockchain starts with the creation of the Genesis Block, which is the first block in the chain.
- Transactions: Users can create transactions that will be included in the next mined block.
- Mining: Mining a block involves solving a Proof of Work problem, which is computationally intensive and secures the blockchain.
- Consensus: The consensus algorithm ensures that all nodes in the network agree on the order of blocks and transactions, even in the presence of conflicting information.


## Future Improvements
- Security Enhancements: Implement more sophisticated cryptographic techniques to secure transactions and blocks.
- Smart Contracts: Integrate smart contract functionality to allow more complex transactions and interactions on the blockchain.

## Acknowledgments
Inspired by the "Learn Blockchains by Building One" tutorial by Daniel van Flymen.
