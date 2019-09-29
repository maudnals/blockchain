#### TCR:
See:

- the tradeoff doc shared on the slack channel
- TCR tutorial by Substrate

https://docs.google.com/document/d/1URR9SnzeRj8NCu8q89VmxFdU1cJriCqgdMy8gRhHttI/edit#
https://medium.com/@tokencuratedregistry/a-simple-overview-of-token-curated-registries-84e2b7b19a06

#### Decentralized Identifiers DID:

DIDs are identifiers that users can use to **identify themselves**.
Mostly blockchain-based.

A DID is two things:

- A unique **identifier** (`did:method:123456789abcdefghi`): the unique ID to look up a DID document. 
  and
- An associated **DID Document** (JSON-LD object): a document that's persistent, immutable. It includes a list of services the DID can be used with, together with their endpoints and an enc+pub key. It's **stored in a central location**.

NB:

- DIDs are good use cases for blockchains
- With DIDs we can do something we've never done before: we can identify things and persons in a secure way, aka emails cannot be forged anymore!
endpoint keys

Zoom on the DID identifier:

- `method`: defines how / where you are going to find the DID. Currently there are 9 registered methods which are all blockchains / distributed ledger technologies.


- It's registered on a **distributed ledger**.?????? is it? what is stored where?
- 
How DIDs are used:


https://medium.com/@adam_14796/understanding-decentralized-ids-dids-839798b91809  
https://w3c-ccg.github.io/did-primer/ 

#### Identity vs right to access:

Snowden warned about this suring web3summit 2019: identity and right to access should be separated.

See 3box approach.
