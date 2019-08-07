#### Truffle

Tooling suite for smart contracts.

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

#### Truffle:

`truffle migrate` to migrate the contracts onto the (local) blockchain.
`truffle console` to open the truffle console and explore the (local) blockchain.
`truffle migrate --reset` to all your migrations from the beginning.

#### Substrate:

A modular toolbox to create blockchain.

- open-source
  It has a 100% abstract “execute block” function encoded in WebAssembly that can be targeted from any one of a number of languages, including C++ and Rust. The execute block function is hot-swappable, meaning you can upgrade your chain’s logic without a hard fork.  
   NB: Substrate 1.0 Beta provides a combined Aura/GRANDPA consensus, with more consensus algorithms to be provided in subsequent releases. Down the road, consensus will be hot-swappable.

Substrate was created in a modular way to give technical freedom but also make functionalities like accounts, balances, governance, and smart contracts as easy as plugging in a library.

forkless runtime upgrade

Parity Substrate is a blockchain development framework with many cool features like upgradable blockchains, modular architecture, customizable block execution logic, and hot-swappable consensus.

Every time Substrate executes a block, it checks its version of the code, being able to switch from native (= node's)runtime to the Wasm runtime on-chain in case the node is not running the most recent version.

Source: https://www.parity.io/substrate-has-arrived/

+++++ https://medium.com/polkadot-network/a-brief-summary-of-everything-substrate-and-polkadot-f1f21071499d
