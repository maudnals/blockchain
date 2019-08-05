Questions:

general:

- mining (= add a transaction onto the blockchain) vs token creation?
- block content - what's inside exactly
- token vs coin
- where does the money come from? "generated"
- mapping blocks/transactions

dApps:

- why are dapps mostly presented in the context of ethereum?
- how does the client dapp knows what version of the smart contract it should talk to? (contrary to normal backend migrations)
- Why is Metamask needed? Would it be so for end-users of the app?
- what are the truffle ports for
- when compiling solidity, we get a json back, is that like an AST? or ABI?
- solidity versions setup

Solidity:

- ???? cant do .length? For example, if we only had 2 candidates in this election, and we try to look up candidate #99, then the mapping will return an empty Candidate structure. This behavior makes it impossible to know how many candidates exist, and therefore we must use a counter cache.

Note: there's a tradeoff speed-security: how do defend the network from attackers while maintaining a certain level of transaction speed for their users?
