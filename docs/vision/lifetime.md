# Lifetime

DropIt is unique in the Polkadot ecosystem in that it is designed to be **ephemeral**.

Whereas most parachains take careful consideration to ensure their chain can scale and persist over time, DropIt will be designed to grow fast and without concern for the far future.

To understand what this means, you need to understand a few topics.

## State Bloat

[State bloat](https://www.techopedia.com/definition/blockchain-bloat) is one of the key long term scaling issues of blockchain systems. As the chain grows, accessing items in the database become more complex due to the construction of the Merkle trie. Also running a full node for the chain becomes more expensive as more storage space is needed to keep the current state of the chain.

Chains like Ethereum are plagued with ["dust accounts"](https://github.com/ethereum/EIPs/issues/168) whose balance is lower than the cost of transaction fees needed to move those balances. Thus these accounts will likely congest the network's Merkle trie forever, and result in a decrease of performance and an increase of costs when running nodes.

Ethereum also faces state scaling issues related to the presence of unused smart contracts and smart contract state. For example, when users push a "Hello, World!" smart contract to Ethereum, they pay a one time fee at the time of the contract deployment, but then those contracts live in the chain state forever, even when they are not being used.

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

Polkadot is uniquely capable of supporting chains without consideration for storage deposits through the creation of disposable parachains.

TODO: perhaps reframe this concept from the term "disposable"

> See the original Polkadot Forum post: [Disposable Parachains (for Airdrops and other ideas)](https://forum.polkadot.network/t/disposable-parachains-for-airdrops-and-other-ideas/5769).

### Data Sharding

Polkadot scales through data and execution sharding. In the context of state scaling, each parachain is responsible to host its own data, and present relevant data needed to execute a block to Polkadot in order for Polkadot to verify the validity of the block.

In the Polkadot ecosystem, the parachain state is maintained by parachain collators. Because collators do not provide any security to Polkadot or the parachain, they can be run by anyone. Only a single copy of the parachain state needs to exist in order to produce new blocks, which allows storage bloat to have a significantly lower impact to the overall network. See [block production](./block-production.md).

### Parachain Footprint

Parachains on Polkadot do not replicate their full state on Polkadot. Instead, only the state root of DropIt is permanently stored on the relay chain.

This means no matter how heavy or bloated DropIt becomes, the Polkadot itself will be unaffected.

### Disposing

Since DropIt is designed without consideration for [state bloat](#state-bloat), the cost for running nodes may increase rapidly.

Because DropIt has completely permissionless and open [block production](./block-production.md), it is up to the collators themselves to determine if it is valuable to continue to run the network.

When all potential collators decide they no longer want to run the network the chain will stop producing blocks. If in the future, anyone wants to submit new transactions to the chain, they can spin up their own collator and build a new block.

### Token Migration

Since DropIt is designed to be ephemeral, it is not suggested that tokens permanently live in the DropIt chain.

When a token accrues enough value or importance to users, it is recommended that the token is teleported to permanent chains like the Polkadot's Asset Hub.

In this case, users will need to establish an existential deposit to hold the token, but the user should find greater value in the token itself.

Also, it is possible for the Polkadot Governance to make a token "sufficient", meaning that users would be able to hold the token on the Asset Hub without any existential deposit, however the barrier for these kinds of tokens are quite high.
