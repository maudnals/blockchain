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

#### Asymetric cryptography:

= public-key cryptography

A cryptographic system that uses pairs of keys:

- **public** keys which may be disseminated widely
- **private** keys which are known only to the owner.

Any person (sender) can ENCRYPT a message using the receiver's PUBLIC key. But that encrypted message can only be DECRYPTED with the receiver's PRIVATE key.

The keys are simply two large numbers that are mathematically related but different.

![alt text](https://lisk.io/content/5-academy/2-blockchain-basics/4-how-does-blockchain-work/2-blockchain-cryptography-explained/6-public-key-cryptography-1.jpg "Logo Title Text 1")

#### Digital signature:

A digital signature:

- secures the data - the signature is generated based on the data so if the data is tampered, the signature will become invalid
- secures the identity of the individual sending it - ownership of a digital signature is always bound to a certain user, so one can be sure that they are communicating with whom they intend to.

Digital signatures are unique to the signer and are created by utilising three algorithms:

A key generation algorithm, providing a private and public key.
A signing algorithm that combines data and private key to make a signature.
An algorithm that verifies signatures and determines whether the message is authentic or not based on the message, the public key and signature.

### Sources

++++ https://medium.com/@julianrmartinez43/understanding-proof-of-work-part-1-586d7ee6b014
++++ https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/proof-of-work
+++ https://cointelegraph.com/explained/proof-of-work-explained
+++ https://blog.goodaudience.com/how-a-miner-adds-transactions-to-the-blockchain-in-seven-steps-856053271476#92ef

https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/blockchain-cryptography-explained
