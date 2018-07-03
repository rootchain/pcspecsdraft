# Transfers

Transfer operations are registered on the spender chain first.

## Conditions

Transfer can remain unspent until conditions to claim it are met.

Most basic conditions to claim a payment include signature with given public key hash.

### Time-locks

Transfer can have a time-lock for the claim.

If not claimed after certain time period it can be claimed back.

## Claim transfer

Claim of a transfer is registered on receiver chain and optionally settled on a main chain.

Transaction should be also be finalized on the spender chain.

Double-claiming it cross-chain will result in transaction invalidation.
