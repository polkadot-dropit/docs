---
sidebar_position: 1
---

# Lifetime

DropIt is unique in the Polkadot ecosystem in that it is designed to be **ephemeral**.

Whereas most parachains take careful consideration to ensure their chain can scale and persist over time, DropIt will be designed to grow fast and without concern for the far future.

To understand what this means, you need to understand a few topics.

## State Bloat

[State bloat](https://www.techopedia.com/definition/blockchain-bloat) is one of the key long term scaling issues of blockchain systems. As the chain grows, accessing items in the database become more complex due to the construction of the Merkle trie. Also running a full node for the chain becomes more expensive as more storage space is needed to keep the current state of the chain.

Chain's like Bitcoin are plagued with ["dust accounts"](https://bitcoinwiki.org/wiki/cryptocurrency-dust) whose balance is lower than the cost of transaction fees needed to move those balances. Thus these accounts will likely congest the network's Merkle trie forever, and result in a decrease of performance and an increase of costs when running Bitcoin nodes.

Chain's like Ethereum face similar state scaling issues related to the presence of unused smart contracts and smart contract state. For example, when users push a "Hello, World!" smart contract to Ethereum, they pay a one time fee at the time of the contract deployment, but then those contracts live in the chain state forever, even when they are not being used.

## Storage Deposits

Chains in the Polkadot ecosystem address this issue through the introduction of storage deposits.

A storage deposit is where users are asked to reserve some amount of token whenever they place data on the blockchain. This deposit cannot be transferred or used while it is reserved. When using an inflationary token like DOT, having a storage deposit is an opportunity cost comparing the value of having that data on chain and gaining interest on the token through staking rewards.

Thus, users are incentivized to clean up data from the blockchain to remove useless data and in order to get their deposit back.

### Existential Deposit

Existential Deposit is a minimum balance that an account needs to hold in order to maintain a presence on the blockchain. The existential deposit is just a storage deposit for the base data needed for each account. For example:

- Nonce
- Balance
- Reference Counters
- etc...

### Ramifications of Storage Deposits

Storage deposits ultimately protect the long term growth of a chain, but also creates overhead for using the chain.

Especially in the context of parachains on Polkadot, even if a user has an existential deposit on Polkadot, they also need to establish an existential deposit on the parachain to use it.

Similarly, the creation and distribution of secondary tokens on chains with an existential deposit are usually prohibitive. In general, this is a good behavior to protect the chain from spam and useless data, but in the current blockchain landscape, this usually limits adoption.

Many other blockchains subsidize the costs of their chain and don't consider long term growth and maintenance in order to specifically bootstrap activity.

## Disposable Parachains

> See the original Polkadot Forum post: [Disposable Parachains (for Airdrops and other ideas)](https://forum.polkadot.network/t/disposable-parachains-for-airdrops-and-other-ideas/5769).

Polkadot is uniquely capable of supporting chains
