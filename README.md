# Chain

## Genesis

It all starts with a genesis chain:

```json
{
  "header": {
    "timestamp": "2018-07-03T11:02:39.2431625+02:00",
    "head_hash": "zHeadAt93QZmSLU6T7YQ2NNJ43hHrTkvMZjW1PPxFYp6TUhwiRdw",
    "exec_hash": "zFuncm698EzQ9mWLBg5TpztVnMF3k74Cc8LH4J5mGPPbzMBouFYS",
    "signed_hash": "zFSec2XV6MQJHimA4ERRK6KTh2JgF8AuJUfyzB43pKG75kzPitDQ"
  },
  "exec_ops": [
    "OP_GENESIS",
    "OP_ASSIGN_POWER [ OP_UINT64 0 OP_UINT64 10000000 OP_PUBKEY 0x020e8b587eab8b5c9a57f3b6d540f01b2ce154a1c4cddad145234e83aad81282f8 ]",
    "OP_ASSIGN_POWER [ OP_UINT64 1 OP_UINT64 10000000 OP_PUBKEY 0x025657544e1355ac629798c62b4a65b917e44ec7b445ee0af334dd5cb5802652ba ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 10000000 ] OP_SIGNATURE 0x1bf0d1ff1eaf18a82dd2c713bb02c66d833bc56e18ef1304f8ee616f96eb21c9cf4591b27bdd7ee40400558c7f5d81b922c2b24c79bacabbe12bbe536eac554efe ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 10000000 ] OP_SIGNATURE 0x1bcecb7639e5cf7b7f7f750b1fc843829e31f38fc16e8fdd0a942df17150d240950a7be03ad0b9cf525c5971aefa06a64d69b876fe1febd72b397ea0fb482c738a ]"
  ],
  "signatures": [
    "HIwPObEgWPFu+MQmUTbQe/U+tqe/E55F5z/LdcBK5N36P9SEnduX/Ul6NMK0DMawqAUSnMM8FeGm3SDJJZKGl98=",
    "G/MDoIyYEmkvEWgmdOWQnbYCef78pMPm2mzaT1olrTasIqtZqjx29WUXPCvME8vRZgzQ28MdnL1+74PVr+PUAtg="
  ]
}
```

Only genesis chain allows empty `prev_hash` and `height` fields and signing with just yet delegated power.
Creation of a chain should be always done on private channels.

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
