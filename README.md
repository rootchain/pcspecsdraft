# Chain

## Genesis

It all starts with a genesis chain:

```json
{
  "header": {
    "timestamp": "2018-07-03T09:03:43.7114081+02:00",
    "head_hash": "zHeadAt9CLih5fYYNkWWfFGvKpZQBNft686e1sBArkg6hYpucJ74",
    "exec_hash": "zFuncm68xVtqrQr1xeefxKKvEvKvbu3rLje4g6tECpoX62cftwbQ",
    "state_hash": "zStateMGz4wQocWbvHVqS1HcbzNzJB5JK3eAkzF9krbSLZiV8cNr",
    "signed_hash": "zFSec2XUzXbWHwP4zYpbEVhhBVaZaGAHNVz7ULotYzhzy4nX4qMJ"
  },
  "exec_ops": [
    "OP_GENESIS",
    "OP_ASSIGN_POWER [ OP_UINT64 0 OP_UINT64 10000000 OP_PUBKEY 0x020e8b587eab8b5c9a57f3b6d540f01b2ce154a1c4cddad145234e83aad81282f8 ]",
    "OP_ASSIGN_POWER [ OP_UINT64 1 OP_UINT64 10000000 OP_PUBKEY 0x025657544e1355ac629798c62b4a65b917e44ec7b445ee0af334dd5cb5802652ba ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 10000000 ] OP_SIGNATURE 0x1bf0d1ff1eaf18a82dd2c713bb02c66d833bc56e18ef1304f8ee616f96eb21c9cf4591b27bdd7ee40400558c7f5d81b922c2b24c79bacabbe12bbe536eac554efe ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 10000000 ] OP_SIGNATURE 0x1bcecb7639e5cf7b7f7f750b1fc843829e31f38fc16e8fdd0a942df17150d240950a7be03ad0b9cf525c5971aefa06a64d69b876fe1febd72b397ea0fb482c738a ]"
  ],
  "signatures": [
    "GyPkPgNaMalkUqI5iUAij/jOns+CUztVC3ViGXIWSvGpTDLYxOc2zpF5Jf90tD5lc5PXPq79N/Ol9dLUwnT7wBQ=",
    "G2CelAazzlZfsFz0yUJbP9q8hWO/Ozd6dJgpO1CGT+VLHNu2Xg6fP9Hlrx7kd/aIQ0fh52dXciXNp3ztjxiGzug="
  ]
}
```

Notice no `prev_hash` field, this indicates genesis chain and it allows to sign it with just delegated power.

Genesis chain is a block generated on a blank sheet, a new chain can be created by anyone.

There is one main chain created by operator, coins are distributed and by that distributing signing power.

## Power

Currency native to each chain is power which is signing power.

## Finalized blocks

Chains have no value unless they are signed by over 51% of delegated signing power.

## Account

User account is a chain whose index can only increment and can never fork.

## Transactions

Transactions are first registered on sender chain and then can be optionally settled on main chain and claimed on receiver chain.

## Transaction validation

Transactions are validated by mechanism similar to UTXO thanks to which we can settle transactions without validating entire user blockchains.

## Off-chain transactions

Chain channels are used to settle, reach consensus and prevent double spending on both on and off-chain transactions.

## Off-chain double spend protection

Protection of on-chain and off-chain transactions is 51% signing power consensus and inability to fork.

When a signing power signs a chain which is finalized block it cannot sign further blocks other than that,
when signing power is used to sign-off forked chain all participants of the network decide to close the (forked source) chain.

Power delegated to public keys used to carry the attack is all lost.
