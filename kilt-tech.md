#### CType:

A Ctype defines the structure of a claim.  
It is based on json-schema.

#### JSON Schema:

JSON Schema is a tool for validating the structure of JSON data.

JSON:  
= “JavaScript Object Notation” = A simple data interchange format.  
Origins: it began as a notation for the web. Interop with JS is very easy since JSON and JS objects are similar.  
Later: JSON has proven useful and simple enough to be used in other contexts.
Data types supported in JSON:

- number
- boolean
- string
- null
- array
- object

https://json-schema.org/understanding-json-schema/about.html#about
https://json-schema.org/understanding-json-schema/reference/index.html

#### Identity (extends PublicIdentity):

- Can be built from a URI such as `//Alice`

NB: In cryptography, a keyring stores known encryption keys. Keyring from Polkadot does key management of user accounts, including generation and retrieval of keyring pairs.  
Ed25519 is the most recommended public-key algorithm available today.

#### CType properties:

- `owner` = owner's public address string (as ss58 public address) = owner's public key = Address of the owner identity
- Is it the same as public signature? "The owner's hash is their public signature" as stated in the whitepaper???

#### Claim:

- The owner should be the claimer: this will be checked in the validation
