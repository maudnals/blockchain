# DID

## TL;DR

DIDs are identifiers that users can use to **identify themselves**.
Mostly blockchain-based.

## 1. Def
A Decentralized Identifier (DID) is a new type of identifier that is:

* globally **unique**;
* **cryptographically verifiable** // cryptographically verify ownership of the identifier;
* globally resolveable with high availability;
* persistent;
* decentralized aka does not require a centralized registration authority.

DIDs are typically associated with cryptographic material (such as public keys and service endpoints) for establishing **secure communication channels**.
Src: w3c

## 0. Problem, vision & use cases

At a superficial level: a DID is simply a new type of identifier.

At a deeper level: DIDs are the core component of a new layer of
decentralized digital identity and PKI for the Internet: the DPKI (decentralized public key infrastructure).

This DPKI could have as much impact on global cybersecurity and cyberprivacy as the SSL/TLS protocol for encrypted Web traffic (now the largest PKI in the world).

DPKI and DID benefits:
- self sovereignty // For self-sovereign identity, which can be defined as a **lifetime portable digital identity** that does not depend on any centralized authority, we need a new class of identifier that fulfills all 5 requirements.
- privacy //

Src: w3c

With DIDs we can do something we've never done before: we can identify things and persons in a secure way, aka:

* Emails cannot be forged anymore;
* Identity theft is solved.

Src: IR

DIDs can be used to securely and privately identify various entities in the W3c Verifiable Credentials ecosystem (issuers, holders, subjects, and verifiers).

More generally, DIDs can be used as identifiers for people, devices and organisations. DIDs are useful for any application that benefits from **self-administered**, cryptographically verifiable identifiers: personal identifiers, organizational identifiers, and identifiers for IoT scenarios.


+++ What exists and why it's not enough

Src: w3c


## 3. Details

### 3.1 DID-Blockchain link

DIDs are good use cases for blockchains.

Src: IR

### 3.2 DID dive-in

DID infrastructure can be thought of as a global key-value database.
The database is all DID-compatible blockchains, distributed ledgers, or decentralized networks. In this virtual database, the key is a DID. The value is a DID document that describes the public keys, authentication protocols, and service endpoints necessary to bootstrap cryptographically-verifiable interactions with the identified entity.

Src: w3c.

So a DID is actually two things:

- A unique **identifier** (`did:kilt:123456789abcdefghi`): the unique ID to look up a DID document. It's registered on a **blockchain**.
and
- An associated **DID Document** (JSON-LD): a persistent, immutable document. It includes a list of services the DID can be used with, together with their endpoints and an encryption+public key. It's **stored in a central location** to be easily looked up.

Src: medium

### 3.3 DID document

+++++++++++++++ Where stored?
+++++++++++++++ What is JSON LD

### 3.4 Resolving DIDs



## 4. Discussions + pros/cons

### 4.1 Identity vs identifiers

Snowden warned about this suring web3summit 2019: identity and right to access should be separated.

See 3box approach.


https://twitter.com/lrettig/status/1163784989626052608?s=19

+ Use of pseudonyms

## Sources

https://medium.com/@adam_14796/understanding-decentralized-ids-dids-839798b91809
https://w3c-ccg.github.io/did-primer/
