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

A key generation algorithm, providing a private and public key.
A signing algorithm that combines data and private key to make a signature.
An algorithm that verifies signatures and determines whether the message is authentic or not based on the message, the public key and signature.
