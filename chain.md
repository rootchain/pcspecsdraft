# Chain

**WIP**

Chain cannot have less than **42%** of entire power delegated to signing.

## Genesis

It all starts with a genesis chain, each account starts with a chain like following:

```json
{
  "header": {
    "timestamp": "2018-07-03T16:03:21.6967617+02:00",
    "head_hash": "zHeadAt99NpDwXh1cMoDEcJqRRGgY8S6v7AQa1Q1rzVdypGVVCCx",
    "exec_hash": "zFuncm68xhwUYFJNPahHfgkYfxTenVuoVkHgW42Ruyrq43QGLWed",
    "state_hash": "zEsT8raaEjJUjS34XpEBVQknmN2oEjXL3Qu79WSTtpmbTLKiUvLP",
    "signed_hash": "zFSec2XV2kCmfbmUQ5F7B6j9KJdVLKvJ18Wf2caNSSCqVgi3HmL7"
  },
  "exec_ops": [
    "OP_GENESIS",
    "OP_ASSIGN_POWER [ OP_UINT64 0 OP_UINT64 10000000 OP_PUBKEY 0x020e8b587eab8b5c9a57f3b6d540f01b2ce154a1c4cddad145234e83aad81282f8 ]",
    "OP_ASSIGN_POWER [ OP_UINT64 1 OP_UINT64 10000000 OP_PUBKEY 0x025657544e1355ac629798c62b4a65b917e44ec7b445ee0af334dd5cb5802652ba ]",
    "OP_ASSIGN_POWER [ OP_UINT64 2 OP_UINT64 10000000 OP_PUBKEY 0x03ff24488ea4d80627cbf3ff2a6c391a9855a609e3aa3c5e30c501df6fe7075177 ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 10000000 ] OP_SIGNATURE 0x1bf0d1ff1eaf18a82dd2c713bb02c66d833bc56e18ef1304f8ee616f96eb21c9cf4591b27bdd7ee40400558c7f5d81b922c2b24c79bacabbe12bbe536eac554efe ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 10000000 ] OP_SIGNATURE 0x1bcecb7639e5cf7b7f7f750b1fc843829e31f38fc16e8fdd0a942df17150d240950a7be03ad0b9cf525c5971aefa06a64d69b876fe1febd72b397ea0fb482c738a ]"
  ],
  "signatures": [
    "G5Xg9SWOUMyyKUHeHkZcmK5sSstPt+VWt4RAJn5wJ+NJN5JaeXj0NOhPqUumMlRU5JpxaAlj9+PRyX9YlwP0g1s=",
    "G0A1JgCI1afJjXbq152Rw6O8nHXyIMBc3T59lK+cvZUqZXWR8eBkDJdu0iG1e6BErX1e4NrspG9C4zcOl897IoU="
  ]
}
```

Example of 2/3 multisig chain genesis. Keys delegate power to themselves.

Genesis chain has always empty `prev_hash` and zero `height` and can be signed with just yet to be delegated power.

Genesis chain is a block generated on a blank sheet, a new chain can be created by anyone.
Creation of a chain should be always done on private channels and should always utilize multisig capability of the chain.

There is one main chain created by operator, coins are distributed and by that distributing signing power.

## Sealing

Chain is not sealed until at least 51% of **all signers** produce a block in their own chain with **witness** operation in it.

## Blocks

Main restriction for blocks is that they cannot be produced with zero operations.

Blocks with higher `height` have to always have higher `timestamp` as well.
