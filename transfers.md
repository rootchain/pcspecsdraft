# Transfers

Transfer operations are registered on the spender chain first.

```json
{
  "header": {
    "index": 1,
    "timestamp": "2018-07-03T17:29:31.8769445+02:00",
    "head_hash": "zHeadAt9Aw2tFedpg1yZT33ZhDVZ36mNvSTqXfMHF8jyYDN1f7MJ",
    "prev_hash": "zHeadAt9DYAW7cTiwQuVzWG1uxxXeNG4B2q3eig3ZqRJqxyTqi4A",
    "exec_hash": "zFuncm68yqR6DAziE8VtxScRxLHije5iD32Bv5mdNtBtCBn3Zk4y",
    "state_hash": "zEsT8raaH3kghsjUTTERsJD4j7B7gjgCFxAqJ5sWh6BmYuWZwBCE",
    "signed_hash": "zFSec2XV3rRoGtZzzrGq65W8LEHvKZgH6AxrByK7dec4dWus98Dc"
  },
  "exec_ops": [
    "OP_SIGNED [ OP_TRANSFER [ OP_UINT64 1000000 OP_PUBKEY_ADDR zFNScYMH1wSYgj67jTxnvJ48XzQnHm5XJqxHuzvpG39e5WbVvL1u ] OP_SIGNATURE 0x1c2f90eecedf9b7a8a5318fe6f9e5acc5c5daa5bcd187aa9385a25fd98f0301f0a1f4863db05578d7562581777b3f9af097f94fe693913ab0365093a4dc9838983 ]"
  ],
  "signatures": [
    "HPNztWw3zUso8aZYOu57zju50On1mfPxnE9NwrKBrsJBCCB2bXzjzlI6tdX/lzzodagRFptNtfFCyvrlkIyk3fM=",
    "G+WJq2eIWn8JPngnAEyXLyuZH+8w/r+1vlDJizd9uyzuDbAPOml5i8W5XdnQzXNxsPAEJ4ZpZcM87pt1d9dSp5s="
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
    "timestamp": "2018-07-03T17:29:31.8819408+02:00",
    "head_hash": "zHeadAt93nxXAJSPVmeVNsWhZcHBpzR52TeWfdERJ6DrQZ1Kg5eE",
    "prev_hash": "zHeadAt9Aw2tFedpg1yZT33ZhDVZ36mNvSTqXfMHF8jyYDN1f7MJ",
    "exec_hash": "zFuncm692CRs4oLWCFzjCwMJr7zqqKrtqouoFaeLaHVDC886RMep",
    "state_hash": "zEsT8raaGxV3V2d5cE5UN5JxjYjpsNQNcT7kakSy9xGGTRpsvfq4",
    "signed_hash": "zFSec2XV3ePyjwCEF4qMMH91BnuVJyeHrL6mfRZUNU7up9bnECdu"
  },
  "exec_ops": [
    "OP_SIGNED [ OP_CLAIM [ OP_CID zFSec2XV4v7WY2h3Wz3SpQFMrFquKNsLpwNqE3apM8u8V5J7Q8jw OP_ID 0 ] OP_SIGNATURE 0x1c9e875652afe77dd7e7f11dda1ab653e5a97a95b58abc4135ad8a9d6e1a4dcad464fcf06e36f1a761000b686c2dcc05dbe41a73907a09350a483262a9dcd5cb25 ]"
  ],
  "signatures": [
    "G5x3q9lBD0g2wA1G+FSe/OqC0q3Xb3Ufb0fncWwCME1/Kqx2QK6zXpZOpyR9AjzwIGnanUauYW3tZ4uJVBb4cZQ=",
    "HIu1ou8DRXxoh+RPYjwd6XMUL99ehFfWXLEUogmewRzBfCr9vXMHPvMf2mHsvKPWeoqZPREsx35Gxk6looa2Sjk="
  ]
}
```

Transaction should be also be finalized on the spender chain.

Double-claiming it cross-chain will result in transaction invalidation.
