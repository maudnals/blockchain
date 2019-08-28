In blockchain, cryptography is for 2 main purposes:   
* Securing the identity of the sender of transactions // see how blockchain wallets use public-key encryption
* Ensuring the past records cannot be tampered with (= are immutable) // see how every new block of data contains a cryptographic hash of the previous block, and how Merkle trees store transactions

Additionally, cryptography is used to:
* make blockchains more efficient // see Simplified Payment Verification, a Merkle tree can be efficiently traverseed to check if a certain transaction has been hashed

Source:  
+++++ https://crushcrypto.com/cryptography-in-blockchain/  
https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/blockchain-cryptography-explained   

#### Cipher: 
An algorithm for performing encryption or decryption.

#### Encoded !== encrypted  
**Encoding**: Transforming data so that it can be consumed by a different system (**usability**). Ex: ascii, unicode, URL Encoding, base64.   
**Encrypting**: Transforming data in order to keep it **secret** from others. Ex: aes, blowfish, rsa     
**Hashing**: Taking an arbitrary input and produce a fixed-length string, to enseure **integrity**. Ex: SHA256   

Source:    
https://danielmiessler.com/study/encoding-encryption-hashing-obfuscation/


#### Asymmetric cryptography:

= public-key cryptography

A cryptographic system that uses pairs of keys:

- **public** keys which may be disseminated widely
- **private** keys which are known only to the owner.

Any person (sender) can ENCRYPT a message using the receiver's PUBLIC key. But that encrypted message can only be DECRYPTED with the receiver's PRIVATE key.

The keys are simply two large numbers that are mathematically related but different.

![](https://lisk.io/content/5-academy/2-blockchain-basics/4-how-does-blockchain-work/2-blockchain-cryptography-explained/6-public-key-cryptography-1.jpg "PKC")

#### Digital signature:

A digital signature is trustworthy and tamperproof:

- secures the data - the signature is generated based on the data, so if the data is tampered the signature will become invalid
- secures the identity of the individual sending it - ownership of a digital signature is always bound to a certain user, so one can be sure that they are communicating with whom they intend to.

Digital signatures are unique to the signer and are created by utilising three algorithms:

* A key generation algorithm, providing a private and public key.
* A signing algorithm that combines data and private key to make a signature.
* An algorithm that verifies signatures and determines whether the message is authentic or not based on the message, the public key and signature.  


#### Nonce:

Arbitrary number than can be used only once.

#### Seed:

= seed phrase = seed recovery phrase = backup seed phrase is a list of words which store all the information needed to recover a wallet.

- Each word assigned to a number.
- The seed phrase can be converted to a number.
- This number is used as the seed integer to generate all the key pairs used in the wallet (deterministic wallet).

The English-language wordlist for the BIP39 standard has 2048 words. So if the phrase contained only 12 random words, the number of possible combinations would be 2048^12 = 2^132 and the phrase would have 132 bits of security. However, some of the data in a BIP39 phrase is not random so the actual security of a 12-word BIP39 seed phrase is only 128 bits. This is approximately the same strength as all Bitcoin private keys, so most experts consider it to be sufficiently secure.

It is not safe to invent your own seed phrase because humans are bad at generating randomness. The best way is to allow the wallet software to generate a phrase which you write down.


#### Sources:  
+++++ https://crushcrypto.com/cryptography-in-blockchain/

#### More crypto links:  
* Very complete book: https://www.garykessler.net/library/crypto.html
* Overview about checksums and hashes https://store.chipkin.com/articles/blockchain-checksums-and-hashes-the-roots-of-blockchains-
