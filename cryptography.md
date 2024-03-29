## Encode !== encrypt !== hash

- **Encode**: Transform data so that it can be consumed by a different system (**usability**). Ex: ascii, unicode, URL Encoding, base64.
- **Encrypt**: Transform data in order to keep it **secret** from others. Ex: aes, blowfish, RSA
- **Hash**: Take an arbitrary input and produce a fixed-length string, to ensure **integrity**. Ex: SHA256

Source:
https://danielmiessler.com/study/encoding-encryption-hashing-obfuscation/

## PlainText --- [Cipher] ---> CipherText

A ciphertext is the result of encryption performed on plaintext using an algorithm, called a cipher.
Cipher: an algorithm for performing **encryption** or **decryption**.

## Encryption vs Signing

These two have very different uses; yet they are also frequently used together: encryption of a signed message is very common.


### Encryption (can be symmetric but here we focus on asymmetric)
##### Summary
Any person (sender) can **ENCRYPT** a message using the receiver's **PUBLIC** key.
But that encrypted message can only be **DECRYPTED** with the receiver's **PRIVATE** key.
##### Example
/
##### Goal
Secrecy
##### Threat model and lifespan
=> Lifespan (relates to threat model):
##### Diagram:
![unnamed](https://www.tutorialspoint.com/cryptography/images/public_key_cryptography.jpg)



### Signing (asymmetric)
##### Summary
##### Example
SSH
##### Goal
Ensures **integrity** and **identity**
=> is **tamperproof** and **trustworthy**. 
(Details:
A digital signature has 2 purposes:
- it secures the **data** - the signature is generated based on the data, so if the data is tampered the signature will become invalid
- it secures the **identity** of the individual sending it - ownership of a digital signature is always bound to a certain user, so one can be sure that they are communicating with whom they intend to. Digital signatures are **unique** to the signer.
)
Threat model:
=> Lifespan (relates to threat model):

Diagrams:
![unnamed](https://user-images.githubusercontent.com/9762897/67575803-9d8f7100-f73d-11e9-917a-bef21ef1bdbb.jpg)
![unnamed](https://www.docusign.com/sites/default/files/ds_subpage_diagram2.svg )


Description: 

When a signer electronically signs a document, the signature is created using the signer’s private key, which is always securely kept by the signer. The mathematical algorithm acts like a cipher, creating data matching the signed document, called a hash, and encrypting that data. The resulting encrypted data is the digital signature. The signature is also marked with the time that the document was signed. If the document changes after signing, the digital signature is invalidated.

As an example, Jane signs an agreement to sell a timeshare using her private key. The buyer receives the document. The buyer who receives the document also receives a copy of Jane’s public key. If the public key can’t decrypt the signature (via the cipher from which the keys were created), it means the signature isn’t Jane’s, or has been changed since it was signed. The signature is then considered invalid.

To protect the integrity of the signature, PKI requires that the keys be created, conducted, and saved in a secure manner, and often requires the services of a reliable Certificate Authority (CA). Digital signature providers, like DocuSign, meet PKI requirements for safe digital signing.

To verify a signature, you need the sender's **public** key.
A digital signature is created by utilising three algorithms:
* A key generation algorithm, providing a private and public key.
* A signing algorithm that combines data and private key to make a signature.
* An algorithm that verifies signatures and determines whether the message is authentic or not based on the message, the public key and signature.  

Sources:
- https://blog.mailfence.com/how-do-digital-signatures-work/ ++++
- https://hedgetrade.com/what-is-a-digital-signature/ +++++







### Differences:
Goal is different
Threat model is different
Lifespan is different

+++++++ Important:
* To prove identity aka sign (aka prove trustworthiness): the client uses her private key and then interacts w/ the server. 
* But to encrypt aka ensure secrecy, the client uses their private key at the end on her side.


prove identity = sign = prove trustworthiness
= authenticate?????
authenticate vs sign vs prove identity

is ssh really authentication??

Thought:
When we think about it, a public key in itself can be used as a method to prove identity (see SSH example below).
That's why public keys are referred to as "authentication methods".
And that's why the ppty called authentication only contains public keys.

Encryption - A message encrypted with someone's public key, can only be decrypted by someone in possession of the matching Private key. **Who was the message really from? No promises there!**

Signing - When someone sees a signed message, they can be sure that the message is unchanged since a person in possession of the matching private key had their hands on it.



### Why Encryption and Signing keypairs should be distinct

You should NOT use the same keypairs for both signing and encryption!

Because (and as far as I see the reason is not technical):

1. Purposes (and so attack vectors) are different.
Someone with your private **signing** key could **impersonate** you, so you never want anyone to get hold of it.
But your workplace might want to escrow (Key escrow is a data security measure in which a cryptographic key is entrusted to a third party i.e. kept in escrow) your private **encryption** key, so that someone else can access your info.

2. Timeframes are different.
You may want a signing key to be valid for a long time so people around the world can check signatures from the past.
But with an encryption key, you often want to roll it over sooner, and be able to revoke old ones without as many hassles.

Sources:

- https://security.stackexchange.com/questions/214971/what-is-the-advantage-of-using-a-digital-signature-over-simple-asymmetric-encryp
- https://security.stackexchange.com/questions/1806/why-should-one-not-use-the-same-asymmetric-key-for-encryption-as-they-do-for-sig 
- https://www.webopedia.com/TERM/K/key_escrow.html

## Zoon on SSH

![](https://pplware.sapo.pt/wp-content/uploads/2017/12/pplware_ssh01.jpg)

## Keys in asymmetric cryptography

asymmetric cryptography = public-key cryptography = a cryptographic system that uses pairs of keys.

In one given keypair:
- **public** key which may be disseminated widely
- **private** key which is known only to the owner.

The keys are simply two large numbers that are mathematically related but different.

![](https://lisk.io/content/5-academy/2-blockchain-basics/4-how-does-blockchain-work/2-blockchain-cryptography-explained/6-public-key-cryptography-1.jpg "PKC")

## Nonce

Arbitrary number than can be used only once.

## Seed

= seed phrase = seed recovery phrase = backup seed phrase is a list of words which store all the information needed to recover a wallet.

- Each word assigned to a number.
- The seed phrase can be converted to a number.
- This number is used as the seed integer to generate all the key pairs used in the wallet (deterministic wallet).

The English-language wordlist for the BIP39 standard has 2048 words. So if the phrase contained only 12 random words, the number of possible combinations would be 2048^12 = 2^132 and the phrase would have 132 bits of security. However, some of the data in a BIP39 phrase is not random so the actual security of a 12-word BIP39 seed phrase is only 128 bits. This is approximately the same strength as all Bitcoin private keys, so most experts consider it to be sufficiently secure.

It is not safe to invent your own seed phrase because humans are bad at generating randomness. The best way is to allow the wallet software to generate a phrase which you write down.

## Cryptography in blockchain

In blockchain, cryptography is for 2 main purposes:   
* Securing the **identity** of the sender of transactions // see how blockchain wallets use public-key encryption
* Ensuring the past records cannot be **tampered** with (= are immutable) // see how every new block of data contains a cryptographic hash of the previous block, and how Merkle trees store transactions

Additionally, cryptography is used to make blockchains more efficient // see Simplified Payment Verification, a Merkle tree can be efficiently traverseed to check if a certain transaction has been hashed.

Source:  
+++++ https://crushcrypto.com/cryptography-in-blockchain/  
https://lisk.io/academy/blockchain-basics/how-does-blockchain-work/blockchain-cryptography-explained   

## Sources:  
+++++ https://crushcrypto.com/cryptography-in-blockchain/

## More crypto links:  
* Very complete book: https://www.garykessler.net/library/crypto.html
* Overview about checksums and hashes https://store.chipkin.com/articles/blockchain-checksums-and-hashes-the-roots-of-blockchains-
