#### Ethereum

An open source platform that enables developers to build and deploy decentralised applications. 2013, Vitalik Buterin.

#### Bitcoin

#### Hyperledger

Hyperledger doesn’t refer to a specific technology, but rather it is a Linux Foundation banner project for multiple blockchain and DLT technologies which support the collaborative development of blockchain-based distributed ledgers. each of which have slightly different characteristics. These frameworks include:

Hyperledger Fabric
Hyperledger Burrow
...

Hyperledger Fabric is a permissioned blockchain infrastructure providing a modular architecture with a delineation of roles between the nodes in the infrastructure, execution of Smart Contracts and configurable consensus and membership services.

#### Hyperledger vs. Ethereum

Ethereum and Hyperledger is the way they are designed and their target audience. Ethereum with it's EVM, smart contract and public blockchain is mostly targeted towards applications that are distributed in nature. On the other hand, Fabric has a very modular architecture and provides a lot of flexibility in terms of what you want to use and what you don't. It's pretty much a la carte and is targeted at businesses wanting to streamline their process by leveraging blockchain technology. For example, it is not possible in Ethereum to have a transaction visible to someone, but not visible to others (a requirement that is very common in business). Fabric allows this and much more.

#### Truffle

Tooling suite for smart contracts.  
`truffle migrate` to migrate the contracts onto the (local) blockchain.
`truffle console` to open the truffle console and explore the (local) blockchain.
`truffle migrate --reset` to all your migrations from the beginning.

#### Ganache

A local in-memory° blockchain, useful to test locally.

_°in-memory DB: DB management system that primarily stores in the main memory (as opposed to disk). It's fast._

#### Metamask

Metamask is "an Ethereum wallet in your b drowser".  
= An extension for accessing Ethereum-enabled Dapps° in the browser.  
How it works: Metamask injects the Ethereum web3 API into every website's JS context, so that Dapps can read from the blockchain.  
_°Dapp: distributed application_

#### Solidity:

Solidity code is compiled to Bytecode for EVM (Ethereum Virtual Machine).

#### Substrate:

A toolbox to create your own blockchain in a modular way.

Substrate:

- give technical freedom
- make functionalities like accounts, balances, governance, and smart contracts as easy as plugging in a library.

- open-source
- forkless runtime upgrade
  It has a 100% abstract “execute block” function encoded in WebAssembly that can be targeted from any one of a number of languages, including C++ and Rust. The execute block function is hot-swappable, meaning you can upgrade your chain’s logic without a hard fork.  
   NB: Substrate 1.0 Beta provides a combined Aura/GRANDPA consensus, with more consensus algorithms to be provided in subsequent releases. Down the road, consensus will be hot-swappable.

Parity Substrate is a blockchain development framework with many cool features like upgradable blockchains, modular architecture, customizable block execution logic, and hot-swappable consensus.

Every time Substrate executes a block, it checks its version of the code, being able to switch from native (= node's)runtime to the Wasm runtime on-chain in case the node is not running the most recent version.

Source: https://www.parity.io/substrate-has-arrived/

+++++ https://medium.com/polkadot-network/a-brief-summary-of-everything-substrate-and-polkadot-f1f21071499d
