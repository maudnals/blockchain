#### Bitcoin address:
 
A Bitcoin address is a hashed version of a Bitcoin public key, to which transactions can be sent.  

What is it for?   
When X sends a payment to Y's address aka public key, Y signs the transaction (with the help of their private key corresponding to the public key used by X), to prove ownership.
This way, X can be sure that the bitcoins have been sent to Y and not to someone else.






00000


It's basically a hashed version of my public key (hashed for convenience, because shorter*).  

<!-- is a **unique identifier** used as a **virtual location** where the cryptocurrency can be sent.    -->


Attention:  
* unlike a digital wallet, a Bitcoin address cannot hold a balance.  
* a Bitcoin address is meant to be a single-use token (how does this work??? isn't there just one address possible for one public key??)
* a Bitcoin transactions do not have any kind of origin-, source- or "from" address. Adresses only receive funds.
* Address !== key. One address --- Private/Public key pair. 

Adress vs. key: 
* Adress = hashed version of my public key
* Bitcoin private key = a randomly generated string (numbers and letters), allowing bitcoins to be spent. 

How it looks like:    
26-35 alphanumeric characters. 
3 possible address formats: 
* P2PKH (pay to public key hash) // starts with `1`
* P2SH // starts with `3`
* Bech32 // starts with `bc1`    

Every public key is 256 bits long and the final hash (your wallet address) is 160 bits long. 

History:    
When Bitcoin first started, people could send the currency to an IP address. Convenient, but made users vulnerable to man-in-the-middle attacks. The Bitcoin address was devised as a more secure alternative.

Where used:  
Most other cryptocurrencies use similar technologies for funds transfer. 

How:  
Digital wallets or Bitcoin clients generate addresses through cryptographic operations:  
* A private key is generated through an asymmetric signature algorithm 
* The public key is derived from the private one.  

----
what addresses are generated when, and what's the randomness?
and what's the diff between an address and a key?  
This string is the public half of an asymmetric key pair.   
what's the encoding? and what's the thing about the checksum?
what is an address exactly used for...? nulti purpose also for signing????
what's a merkle tree???
what's a checksum???
encode vs encrypt
how is a signature pair generated and used vs how is a encryption pair generated and used
simple hashing def
simple encryption def
how does a wallet work?  
the private key is randomly generated... ?

Sources: 
* https://whatis.techtarget.com/definition/Bitcoin-address
* https://en.bitcoin.it/wiki/Address
* https://bitcoin.stackexchange.com/questions/13059/whats-the-difference-between-a-wallet-and-an-address
* https://www.dummies.com/software/other-software/bitcoin-public-private-keys/ 


#### Wallet:   
A wallet:  
* is just an abstract construct
* is actually a keyring, aka it stores my bitcoin addresses and related key pairs
* sums the funds up and presents them as a single total balance - under the hood, however, these balances are stored publicly in the blockchain

How it looks like:    
The format of the wallet is stereotypically a text file on disk.

So: 
- one uses someone else's address to send Bitcoin
- one uses their own wallet to encrypt, import/export and back up 

Sources:     
* https://bitcoin.stackexchange.com/questions/13059/whats-the-difference-between-a-wallet-and-an-address


Why backup my wallet?   
- if I lose it / delete it, then the funds still exist but I won't be able to access them.
- Also note: my entire wallet should be backed up - not just the private keys for your visible Bitcoin addresses. Because wallets use many hidden private keys internally.

What happens if ?
How do I sign a transaction, as a sender? aka how is the money taken from my account?  

Sources: 
* https://bitcoin.org/en/secure-your-wallet#backup 


#### Deterministic wallet (HD Wallet) 
In a deterministic wallet, the keys are derived from a passphrase (a specific seed, masterkey or password) instead of a random seed.      
Benefits:   
* **Still private**: You can generate different receiving addresses every time you receive bitcoins. // non-HD wallets: a pair of private/public keys was randomly generated to have different addresses each time, which garanteed privacy and security (no one can see all movements relate to one given address over time, since the addresses keep changing)
* **But easier backup**: You need to backup only one key (i.e. “seed key”). It is the only backup you will ever need. // in non-HD wallets: because of the randomness mentioned above, you needed to backup your whole key store (= wallet) at each single transaction, which was annoying.  

Basically HD wallets add one layer of stability between the user (wants stability over time for usability) and their adresses (need variation over time for security and privacy).

Source: 

NB: 
* an HD wallet is a keyring in the cryptographic sense
* your receiving address changes every time.

Sources: 
* https://bitcoin.org/en/secure-your-wallet#backup 
* https://coinsutra.com/hd-wallets-deterministic-wallet/


#### Libra:

Afinancial instrument that uses blockchain technology to enable transactions, using a digital currency managed by a consortium of private companies.

#### Calibra:

The payments subsidiary that Facebook owns.
