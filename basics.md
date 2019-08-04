#### Blockchain:
A blockchain is a decentralized, immutable database.   
 
decentralized  
P2P  
crypto


#### Decentralized vs distributed: 

#### Block:  
A blockchain's records are called blocks. 
They're linked using cryptography.  
Each block contains:  
* a cryptographic hash of the previous block  
* a timestamp  
* transaction data (generally represented as a Merkle tree).



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

### Sources

++++ https://medium.com/@julianrmartinez43/understanding-proof-of-work-part-1-586d7ee6b014
++++ https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/proof-of-work 
+++ https://cointelegraph.com/explained/proof-of-work-explained
+++ https://blog.goodaudience.com/how-a-miner-adds-transactions-to-the-blockchain-in-seven-steps-856053271476#92ef

------- 

Questions:

general:
- mining (= add a transaction onto the blockchain) vs token creation?
- block content - what's inside exactly
- token vs coin
- where does the money come from? "generated"

dApps:
- why are dapps mostly presented in the context of ethereum?
- how does the client dapp knows what version of the smart contract it should talk to? (contrary to normal backend migrations)

Solidity:
- ???? cant do .length? For example, if we only had 2 candidates in this election, and we try to look up candidate #99, then the mapping will return an empty Candidate structure. This behavior makes it impossible to know how many candidates exist, and therefore we must use a counter cache.

Note: there's a tradeoff speed-security: how do defend the network from attackers while maintaining a certain level of transaction speed for their users?  
