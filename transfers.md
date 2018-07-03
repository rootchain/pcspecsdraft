# Transfers

Transfer operations are registered on the spender chain first.

```json
{
  "header": {
    "index": 1,
    "timestamp": "2018-07-03T17:15:42.795461+02:00",
    "head_hash": "zHeadAt9843LAa4t4rdKyJZLaxCwGMRKuHYxQRV2a8Gh69rK1Dzh",
    "prev_hash": "zHeadAt94YCArGcowMhreveVBWgiocFZinhoZgwGGs81pcDBM8af",
    "exec_hash": "zFuncm68yqR6DAziE8VtxScRxLHije5iD32Bv5mdNtBtCBn3Zk4y",
    "state_hash": "zEsT8raaFywo6yVoxXvujNtE3PNAHeij47ZCAN2vTQ9RRcshtFXz",
    "signed_hash": "zFSec2XVGWJxNatYmTXKBTm1FKUekFSP77egno3QZLNsZDVMLCBZ"
  },
  "exec_ops": [
    "OP_SIGNED [ OP_TRANSFER [ OP_UINT64 1000000 OP_PUBKEY_ADDR zFNScYMH1wSYgj67jTxnvJ48XzQnHm5XJqxHuzvpG39e5WbVvL1u ] OP_SIGNATURE 0x1c2f90eecedf9b7a8a5318fe6f9e5acc5c5daa5bcd187aa9385a25fd98f0301f0a1f4863db05578d7562581777b3f9af097f94fe693913ab0365093a4dc9838983 ]"
  ],
  "signatures": [
    "G2Ja290yLhDirXzIZyFRRIx/1kw2/BBtrEBcXYT7GUAkOwvZyNCy0kfEFb+JG6H/asM8JWvo+a99IDX7FT9W1y0=",
    "G3SsytOFJcy+u4joNIuhvWWZbBYEk0mmg3oz2yILlXTZRItKke8I4dYprT1dEYSv8GlF+fsbLsE6FLnAIKxQbw4="
  ]
}
```

## Conditions

Transfer can remain unspent until conditions to claim it are met.

Most basic conditions to claim a payment include signature with given public key hash.

### Time-locks

Transfer can have a time-lock for the claim.

If not claimed after certain time period it can be claimed back.

## Claim transfer

Claim of a transfer is registered on receiver chain and optionally settled on a main chain.

```json
{
  "header": {
    "index": 2,
    "timestamp": "2018-07-03T17:26:38.2385927+02:00",
    "head_hash": "zHeadAt8yeztQLd9aCT7m4QRZn5fidSgdU54UDsK56JPL665p2eE",
    "prev_hash": "zHeadAt968434JgLYtcvNhNak6YzWiBVxiaYgDKJWxXvidgVT1iV",
    "exec_hash": "zFuncm6927JHsNTJermLQz39uEDKEzkebGWDukiwgdXRWBitbbrF",
    "state_hash": "zEsT8raaHXmgPE7E9e7LfS2fuqhg4QrveKpeUKbzEQ1b8v4eBdP5",
    "signed_hash": "zFSec2XVAYhuXdLCLLbc8tyVpHqzvQdCUpCkbzKxSzjXMbMKxs5n"
  },
  "exec_ops": [
    "OP_SIGNED [ OP_CLAIM [ OP_CID zFSec2XVBPZzaJXYgRqyJwn5KHDr3mDX5tkodHDohekwicWnyKRU OP_ID 0 ] OP_SIGNATURE 0x1bdeee9b3df4d7361d4e3fdbe303fc86b1af42b35e446b44291e46fed712f7983f35def1f4db852212e1ce9057fd4663fa8a8a9f0e0e568fd9e87ae557d91728c2 ]"
  ],
  "signatures": [
    "GzSYYSu5BDIFHBa1EuYlA/QMD788IIt2HviBn240nJ0POv/Nf2GvGEn74k3FYZprDxM6qkjFU+unDFSZoVcyB6o=",
    "G8jj5KMddkjkHhzCw2x+wxwnD6DVFT/xc46M/iSEeOioOcQQfGEcejtp/6b7YxBUktiSYxP7FGl70nXzj5VXPvw="
  ]
}
```

Transaction should be also be finalized on the spender chain.

Double-claiming it cross-chain will result in transaction invalidation.
