Questions:
- mining (= add a transaction onto the blockchain) vs token creation
- block content


#### Nonce:
Arbitrary number than can be used only once

#### Proof Of Work:
Blockchain is a decentralized database, so it needs to be secured by properly incentivizing participants in the network.

This means:
- financially rewarding participants that facilitate the goals of the network
- making attackers waste money when they attack the network.

And securing the network this way is the job of the consensus algorithm. 
There are several types of consensus algorithms:
- proof of stake
- proof of work

Note: there's a tradeoff speed-security: how do defend the network from attackers while maintaining a certain level of transaction speed for their users?

What miners do:
aka what solving a block really looks like
A miner:
- verifies transactions
- organizes these transactions into a block
- distributes completed blocks (already solved) throughout the network, this happens very quickly and is not energy intensive. What is energy intensive is the “lottery system” or “puzzle” that miners need to solve in order to create a valid block.

// to be continued

#### Consensus algorithm: 
A process in computer science used to achieve agreement on a single data value among distributed systems.


++++ https://medium.com/@julianrmartinez43/understanding-proof-of-work-part-1-586d7ee6b014
++++ https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/proof-of-work
