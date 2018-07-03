# Blocks

Main restriction for blocks is that they cannot be produced with zero operations.

Blocks with higher `height` have to always have higher `timestamp` as well.

## Genesis

Genesis chain has always empty `prev_hash` and zero `height` and can be signed with just yet to be delegated power.

Creation of a chain should be always done on private channels and should always utilize multisig capability of the chain.

## Sealing

Chain is not sealed until at least 51% of **all signers** produce a block in their own chain with **witness** operation in it.