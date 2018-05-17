# Decentral Bank Forkfulness (document in progress)

The Decentral Bank Network (DBN) is a set of bank branches (smart contracts) among many distributed ledgers which the equity holders decide to accept assets on. Because of this, it is important to clearly define the forkfulness properties of such a network. 

The DBN is much more resistant to forks to its network than most distributed ledger networks because it is one of the first inter-ledger protocols, meaning that the network itself encompasses on potentially many chains with their own Byzantine consensus rules. 

On the contrary, this also means that respective ledgers can fork their networks without direct input from decentral bank equity holders and users. 

## Equity holder forks

Equity tokens are used to vote on the bank's monetary policy. Thus, it is important to understand how forks in the equity token distribution affect decentral bank monetary policy. Regardless of the ledger of the decentral bank tokens (whether ERC20 Ethereum tokens, its own proof of stake blockchain, or other general compute ledger), forks are a possibility due to the nature of permissionless, peer-to-peer systems. 

Bank branche smart contracts would only listen to actions signaled from the canonical equity token ledger. This means that each bank branch smart contract must have the proper logic for checking the canonical-ness of an equity token vote to see if action is signaled by the "real" equity holders. 

In order for equity token forks to start new decentral bank networks, they would need to change the bank branch smart contract logic so that the root hash of the equity token distribution refers to their new fork rather than the root hash which references the canonical chain. 

## Bank branch forks

Assume there is an ETH bank branch smart contract which resides in the canonical ETH ledger. This ETH bank branch smart contract smart contract has the proper logic to check for equity holder actions from the canonical distribution of equity tokens. Next, assume that the canonical ETH ledger forks due to some community contentious event such as a DAO-like event. There is now an ETH bank branch smart contract and an ETH2 bank branch smart contract. Both of these smart contracts have the same logic for checking for the canonical equity holder distribition when listening for policy actions, thus allowing ETH2 bank branch to also be under control of the canonical equity holders. 

Any ledger which contains a decentral bank branch can fork. In such a case, both the canonical smart contract and the forked bank branch remain under control of the canonical equity holder distribution.  

## Conclusion

Decentral Bank is a complex system of inter-ledger smart contracts which listen to a canonical equity token distribition. When ledgers which contain bank branches fork, both the canonical branch and the forked branch remain under the control of the canonical equity holder distribution. When equity holder tokens 

## References 

https://ethresear.ch/t/in-favor-of-forkfulness/1225
