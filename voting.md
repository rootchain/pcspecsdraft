# Cross-chain voting

Cross-chain voting is designed so it can be used to construct proof-of-stake blockchain as well as providing
secure witness voting side-chain for proof-of-work blockchain such as Bitcoin or Ethereum to enable mainchain enforced collateral based cross-chain trading.

Votes for such proof-of-work side-chains could be split as votes should reflect how the user sees the world around not just it's own opinion.

## Operations

Design of operations desire functionality of cross-chain voting.

### Vote

Vote operation can be performed by anyone but power of the vote is delegated per-chain and treated as such.

### Witness

Finalized blocks are registered cross-chain by `witness` operation.

```json
{
  "header": {
    "height": 1,
    "timestamp": "2018-07-03T11:02:39.2451611+02:00",
    "head_hash": "zHeadAt95c3XpbaJ3DmKcsZ4xaEkLh3zR4yyg8aHR2CMPbnCmxGS",
    "prev_hash": "zFSec2XV1CG6DsUkFvuebtEqyDGMLrL8QNktw8nrSt2KFw42jeYG",
    "exec_hash": "zFuncm698EjRYszTuwTUyCVr7wuETsSUAfSPa2V7VtvRzntiZ3vy",
    "state_hash": "zEsT8raaKyG9e7LSoPLZzFGnvprQD1PpY2crCbqc9NoN8MHcc4rS",
    "signed_hash": "zFSec2XV6CKJhryAugfazNu4y4oH7KzWeoJhhE8u8vrKYsNWsXbX"
  },
  "exec_ops": [
    "OP_WITNESS [ OP_CID zFSec2XV6CKJhryAugfazNu4y4oH7KzWeoJhhE8u8vrKYsNWsXbX ]"
  ],
  "signatures": [
    "HPtdcu+bUtkEB6GBlHAG0wcStxk1iJpXKkGkGu7p1UutXxLzLypf2nr79oGigWGp+gXI7S6G/P091IYA4NALgzI=",
    "HABIye7t6u4EZMZkv6xLmtZaQgGl8zNktpYdCcjMTrEXeckuSUbsbPgNG8HAYWzcD/8iw3UFJB+lEKw6Du2iD4A="
  ]
}
```

### Witness fork

Chains can log witnessing of a fork.

```json
{
  "header": {
    "height": 1,
    "timestamp": "2018-07-03T11:02:39.2451611+02:00",
    "head_hash": "zHeadAt95c3XpbaJ3DmKcsZ4xaEkLh3zR4yyg8aHR2CMPbnCmxGS",
    "prev_hash": "zFSec2XV1CG6DsUkFvuebtEqyDGMLrL8QNktw8nrSt2KFw42jeYG",
    "exec_hash": "zFuncm698EjRYszTuwTUyCVr7wuETsSUAfSPa2V7VtvRzntiZ3vy",
    "state_hash": "zEsT8raaKyG9e7LSoPLZzFGnvprQD1PpY2crCbqc9NoN8MHcc4rS",
    "signed_hash": "zFSec2XV6CKJhryAugfazNu4y4oH7KzWeoJhhE8u8vrKYsNWsXbX"
  },
  "exec_ops": [
    "OP_WITNESS_FORK [ OP_CID zFSec2XV6CKJhryAugfazNu4y4oH7KzWeoJhhE8u8vrKYsNWsXbX ]"
  ],
  "signatures": [
    "HPtdcu+bUtkEB6GBlHAG0wcStxk1iJpXKkGkGu7p1UutXxLzLypf2nr79oGigWGp+gXI7S6G/P091IYA4NALgzI=",
    "HABIye7t6u4EZMZkv6xLmtZaQgGl8zNktpYdCcjMTrEXeckuSUbsbPgNG8HAYWzcD/8iw3UFJB+lEKw6Du2iD4A="
  ]
}
```
