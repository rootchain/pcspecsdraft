# Forkability

There are two distinct types of chains in the whole system.

## Root chains

Chains described in this specification can never be forked.

Once block is finalized it cannot be forked or otherwise whole chain is terminated at pre-fork height.

Read more about implications of inforkability [below](#implications).

## Witnessed chains

Rootchain is designed for cross-chain voting for itself but also for other existing types of systems.

In case of Proof-of-Work systems it is easier for attacks to take place as long as block producers are anonymous,
have nothing to loose except money put into computation power required to perform such attacks.

While forks can occur it is almost impossible to trade securely with near-instant transaction settlement,
nevertheless we are using voting to witness, vote and detect the possible network fork and by that provide
more secure information available for cross-chain trading systems of proof-of-work blockchains based assets like Bitcoin and Ethereum.

## Implications

Trivial implications that can be tought like keeping track of own chain will be solved for most users. It is open question when it comes to keeping track of entire (custom) and even bigger chains than main net.
