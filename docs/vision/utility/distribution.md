# Distribution

DropIt provides multiple ways to distribution custom tokens to the Polkadot community.

## Polkadot Snapshot

Using the state root of Polkadot, token distributors are able to distribute tokens to existing DOT holders exactly in proportion to the amount of DOT they are holding on the Polkadot relay chain.

DropIt provides functionality to store the state root of a finalized relay chain block, and DOT holders are able to provide a Merkle proof to the chain with the amount of DOT they held at that block, and permissionlessly claim a distribution based on that amount.

This option is preferable when directly trying to distribute assets to the existing Polkadot community.

## Custom Merklized Snapshot

Token distributors can provide their own Merkle root representing a Merkle trie of accounts and amounts to be distributed to those accounts.

Users can then provide a Merkle proof to the chain with their entry in that Merkle trie, and permissionlessly claim their distribution amount.

This option is preferable when trying to distribute assets to a large number of users, where only a single piece of data needs to be uploaded to the chain to begin the distribution. There is complexity pushed into generating the Merkle trie and having users submit valid proofs to collect their tokens.

## Custom Raw Snapshot

Token distributors can provide a raw list of accounts and amounts representing the distribution of a token.

Users can then submit a claim for that amount.

This option is preferred when needing to minimize the complexity for generating the distribution table or for users to claim their distribution. There is overhead needed to submit transactions which will populate the raw snapshot.

## Crowdfund

Token distributors have the ability to accept DOT from users in order to generate a distribution table.

The collected DOT will be transferred to the token distributor, and DOT contributors can permissionlessly claim their tokens based on the amount contributed.
