#### Transaction lifecycle (valid for ₿ and others):

1. A user signs off on a transaction from their wallet application. 
2. The transaction is broadcasted to the network. 
3. A/several nodes verify it (basic checks, see https://blog.kaiko.com/an-in-depth-guide-into-how-the-mempool-works-c758b781c608 ) and include it in their pool (= mempool = pool of unconfirmed transactions).
4. Miners on the network select transactions from these pools and form them into a ‘block’. A block is a collection of transactions (still unconfirmed at that moment) + some metadata. Every miner constructs their own block of transactions. Multiple miners can select the same transaction to be included in their block.
5. Miners attempt to solve the PoW (To add this block of transactions to the blockchain (to have all other miners and nodes register the transactions), the block first needs a signature also referred to as a proof of work.) 
6. The miner that solves PoW first (=finds an eligible signature for its block), broadcasts this block and its signature to all the other miners.
7. Other miners:  
   - verify the signature’s legitimacy // by taking the string of data of the broadcasted block, and hashing it to see if the output hash indeed matches the included signature
   - If it is valid: confirm the block validity and agree that the block can be added to the blockchain (they "reach consensus"). 
   - The block can now be added to the blockchain, and is spread across all other nodes on the network. 
8. Other nodes will accept the block and save it to their transaction data as long as the transactions inside the block correspond correctly with the current wallet balances (transaction history) at that point in time.
9. Every block added afterwards counts as a confirmation for this transaction. 

NB: After a new block is added to the blockchain, all miners need to start over again at step three by forming a new block of transactions. Miners cannot continue (well, they can, but that is quite irrelevant in this article) mining aka solving the problem of the block they were working on themselves because: 
* it may contain transactions that have been confirmed by the last block that was added to the blockchain (remember, multiple miners can select/include the same transactions(s) in the block they are solving) and therefore some of these transactions may now no longer be valid, making the block invalid as a whole.
* every block needs to add the hash output (signature) of the last block that was added to the blockchain into their metadata. This is what makes it a blockchain. If a miner keeps mining the block they were already working on, other miners will notice that the hash output does not correspond with that of the latest added block on the blockchain, and will therefore reject the block.
 
--   
Sources:  
* https://99bitcoins.com/bitcoin/mempool/ 
* ++++++++ https://blog.goodaudience.com/how-a-miner-adds-transactions-to-the-blockchain-in-seven-steps-856053271476#92ef

#### Core ₿ concepts:  
* Public key ~ address: used to received bitoins
* Private key: used to send bitcoins


#### Cryptographic scheme:  
Bitcoin makes heavy use of the cryptographic hash function SHA256, which stands for Secure Hash Algorithm 256-bit.   
The SHA algorithms were originally developed by the NSA. 

#### ₿ address:
 
A hashed version of a ₿ public key, to which transactions can be sent. Unique identifier.   

```javascript
public key ---[hashing]---> address

256bits                     160bits
```

What it is for:   
When X sends a payment to Y's address aka public key, Y signs the transaction (with the help of their private key corresponding to the public key used by X), to prove ownership.
This way, X can be sure that the bitcoins have been sent to Y and not to someone else. The ₿ adress replaced the former IP address approach, which made users bulnerable to MITM attacks (https://en.bitcoin.it/wiki/IP_transaction) . 

Key points:     
* Adresses only **receive** funds. A ₿ transaction doesn't have an origin-, source- or "from" address. 
* A ₿ address cannot hold a balance (unlike a digital wallet)  
* A ₿ address is meant to be a **single-use token**
* Address !== key. One address --- Private/Public key pair. 

How it looks like:    
26-35 alphanumeric characters. 
3 possible address formats: 
* P2PKH (pay to public key hash) // starts with `1`
* P2SH // starts with `3`
* Bech32 // starts with `bc1`    


Where used:  
In most cryptocurrencies use similar technologies for funds transfer. 

How:  
Digital wallets or ₿ clients generate addresses through cryptographic operations:  
* A private key is generated through an asymmetric signature algorithm 
* The public key is derived from the private one.  

--  
Sources: 
* https://whatis.techtarget.com/definition/Bitcoin-address
* https://en.bitcoin.it/wiki/Address
* https://bitcoin.stackexchange.com/questions/13059/whats-the-difference-between-a-wallet-and-an-address
* https://www.dummies.com/software/other-software/bitcoin-public-private-keys/ 


#### Mempool:    
A node's holding area for all pending transactions, that are waiting to be picked up by a miner.     
Each node has its own mempool, and they vary in size (transaction size, hardware capacity).  

Unit of the mempool size: unit of memory aka megabyte (MB). 

When the node memory gets full:    
Unlike mining, there is no financial incentive for running a node. Therefore, the hardware dedicated to it tends to be limited and so a node’s mempool often max out its RAM.    
If the mempool size gets too close to the RAM capacity, the node sets up a minimal fee threshold. Transactions with fees per kB lower than this threshold are immediately removed from the Mempool and only new transactions with a fee per kB large enough are not allowed access to the Mempool.   

--  
Sources:   
* ++++ https://blog.kaiko.com/an-in-depth-guide-into-how-the-mempool-works-c758b781c608
* https://www.mycryptopedia.com/mempool-explained/ 

#### ₿ confirmation:   

The number of blocks in the blockchain that have been accepted by the network since the block that includes the transaction.   
Aka "how deep is the block containing transaction X".  

Higher confirmation   
= Higher difficulty of a double spend attack (= forged transaction)   
= Higher security.  
 
6 is standard for most transactions to be considered secure.   
Until then, the transaction is "unconfirmed".  
Confirming a transaction takes about 1 hour (10 minutes / block).  

--    
Sources: 
* https://bitcoin.stackexchange.com/questions/146/what-are-bitcoin-confirmations
* +++++ https://www.buybitcoinworldwide.com/confirmations/


#### ₿ miner fees ("bitcoin fees" for short):  
Bitcoin miners confirm and secure transactions by adding blocks to the blockchain.   
They need to be paid for their work.  
So fees are attached to transactions.   

Unit: Satoshi per byte (of transaction data).

Key points:  
* Fees are paid by the **sender** 
* Fees are **dynamic**: they rise/fall depending on ₿ network demand and limited ₿ network space.
* **Higher is faster**: Since miners want to maximize their profit, they will prioritize transactions that have a larger fee to size° ratio (**feerate** for short).  
* **Complex but hidden**: in practice, wallets calculate the fees for the user (should be set to dynamic).  

So, when solving a block, miners receive: 
* The fees attached to any transactions on that block.
* A reward for solving the block (13BTC at the moment)

_°Size: each ₿ transaction has a size. More inputs (= references to past transactions, adding up to the amount you own) --> larger. More outputs (= destination addresses) --> larger._   

--  
Sources:   
* Overview: https://support.bitpay.com/hc/en-us/articles/115003393863-What-are-bitcoin-miner-fees-Why-are-miner-fees-so-high-
* Details of a transaction: https://99bitcoins.com/bitcoin/fees/ 

#### Satoshi: 
Value: 0.00000001 BTC = one hundredth million of a ₿ = 10^-8 bitcoins  
Symbol: シ or SAT   

Source: https://cointelegraph.com/news/what-is-a-satoshi-the-smallest-unit-on-the-bitcoin-blockchains

#### Wallet:   
* Just an abstract construct
* A store for my key pairs and related ₿ addresses (aka a keyring)
* Sums the funds up and presents them as a single total balance - under the hood these balances are stored publicly in the blockchain

How it looks like:      
A text file on disk. `wallet.dat`

Why backup your wallet:    
- if the wallet is lost/deleted: the funds still exist but are not accessible

How to backup your wallet:  
The entire wallet should be backed up - not just the private keys for the visible ₿ addresses. Because wallets use many hidden private keys internally.   

How often:   
- If HD wallet: just once is enough. Unless you encrypt it in between, then need to do a backup again, because after encryption keys are flushed. 
- Else: each time new keypairs are generated. 

--  
Sources: 
* https://bitcoin.org/en/secure-your-wallet#backup 
* https://bitcoin.stackexchange.com/questions/13059/whats-the-difference-between-a-wallet-and-an-address

#### Deterministic wallet (HD Wallet = Hierarchical Deterministic) 
Wallet for which the keys are derived from a passphrase (a specific seed, masterkey or password) instead of a random seed.      
Benefits:   
* **Still private**: You can generate different receiving addresses every time you receive bitcoins. // non-HD wallets: a pair of private/public keys was randomly generated to have different addresses each time, which garanteed privacy and security (no one can see all movements relate to one given address over time, since the addresses keep changing)
* **But easier backup**: You need to backup only one key (i.e. “seed key”). It is the only backup you will ever need. // in non-HD wallets: because of the randomness mentioned above, you needed to backup your whole key store (= wallet) at each single transaction, which was annoying.  

=> HD wallets add one layer of stability between the user (wants stability over time for usability) and their adresses (need variation over time for security and privacy).

Sources: 
* https://bitcoin.org/en/secure-your-wallet#backup 
* https://coinsutra.com/hd-wallets-deterministic-wallet/


#### Libra:

A blockchain-based digital currency managed by a consortium of private companies.

#### Calibra:

The payments subsidiary that Facebook owns.
