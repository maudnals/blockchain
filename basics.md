#### Blockchain:

A blockchain is a decentralized, immutable database.

Core concepts:

- P2P
- crypto

#### Decentralized vs distributed:

A decentralized system is a subset of a distributed system. Decentralized means that there is no single point where the decision is made.

#### Block:

A blockchain's records are called blocks.  
They're linked using cryptography.  
Each block contains:

- a cryptographic hash of the previous block
- a timestamp
- transaction data (generally represented as a Merkle tree).

#### Mining:

#### Nonce:

Arbitrary number than can be used only once.

#### Proof Of Work:

Blockchain is a decentralized database, so it needs to be secured by incentivizing participants in the network.

This means:

- reward participants that facilitate the goals of the network
- make attackers waste money.

And securing the network this way is the job of the consensus algorithm.
2 types of consensus algorithms:

- proof of stake PoS
- proof of work PoW

A miner:

- verifies transactions
- organizes these transactions into a block
- distributes completed blocks (already solved) throughout the network, this happens very quickly and is not energy intensive.
- What is energy intensive is the “lottery system” or “puzzle” that miners need to solve in order to create a valid block.

// to be continued

#### Consensus algorithm:

A process in computer science, used to achieve agreement on a single data value among distributed systems.

#### Smart contract:

A smart contract is a piece of code that executes the business logic of a dApp ; aka is responsible for reading and writing data to the blockchain.
How it runs: it's executed by the Ethereum Virtual Machine (EVM).
What it is: it's usually written in Solidity.

#### Asymetric cryptography

= public-key cryptography

A cryptographic system that uses pairs of keys:

- public keys which may be disseminated widely
- private keys which are known only to the owner.

Any person (sender) can encrypt a message using the receiver's public key. But that encrypted message can only be decrypted with the receiver's private key.

The keys are simply two large numbers that are mathematically related but different.

### Sources

++++ https://medium.com/@julianrmartinez43/understanding-proof-of-work-part-1-586d7ee6b014
++++ https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/proof-of-work
+++ https://cointelegraph.com/explained/proof-of-work-explained
+++ https://blog.goodaudience.com/how-a-miner-adds-transactions-to-the-blockchain-in-seven-steps-856053271476#92ef
