# Chain

**WIP**

Chain cannot have less than **42%** of entire power delegated to signing.

## Genesis

It all starts with a genesis chain, each account starts with a chain like following:

```json
{
  "header": {
    "timestamp": "2018-07-10T19:07:53.2727726+02:00",
    "head_hash": "zHeadAt96Dkyhp32wJYjzv4NHm6jqSBKzVEPBK2pBVmQnvNgYuRx",
    "exec_hash": "zFuncm692Z5CvNpTUv5pLz8tjw1Tp4HeRWH6ptxvRBZCtGAn54oA",
    "state_hash": "z45oqTS8HpwMPrbFWZUomZGtdan4oWSqnTarsN7aH442oXJdafj",
    "signed_hash": "zFSec2XVDESfaxnZb3qjfwxGkH5fUZRChfCAr1WYHUfea9RJ1fGs"
  },
  "exec_ops": [
    "OP_ASSIGN_POWER [ OP_UINT64 1000000 OP_CID zFNScYMHAiBJPJcT9ri2cNwKTJfitbRcE2PSfMKQj272C6A5Fs25 ]",
    "OP_ASSIGN_POWER [ OP_UINT64 1000000 OP_CID zFNScYMH8j9JuHxLR5KLsNP528LuLBi7ToCrh9tmdLb85pWno5Bg ]",
    "OP_ASSIGN_POWER [ OP_UINT64 1000000 OP_CID zFNScYMH9HiRhyWx8nhwLmo4UfxegoSUTE7nQ17Lji2hzDVJnszf ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 1000000 ] OP_SIGNATURE 0x1b79b046893a70d76d8b228deb2b1da4eec5253f89c87d37fc805b47b1182616aa0675407332d7b4179ec633bc4ea0747d8ddf42f93ae891e292602861a3be4332 ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 1000000 ] OP_SIGNATURE 0x1c079e6a5c5a0c832759008df68b521a7e9451239dcb16af3f0e265fa59230df897b1d98f7254b8f35c80828cccb81089ad2b38b5e2c0134102e401c80e24683cc ]",
    "OP_SIGNED [ OP_DELEGATE_POWER [ OP_UINT64 1000000 ] OP_SIGNATURE 0x1cc03322f986677b8f5b689d7daa711be604291704c747570e690cb2484588809b4250c39ae0cc7dba7562b440fd3afe0eadd281c4552d8748dec662295e855414 ]"
  ],
  "signatures": [
    "HPTR7L5Sw3O23EDVA+K4CB6idJxlSVAMgAhi7LNEKpo0Q/1iixp8h8eCUePlhdaIG6eN2k5T+JH+WoZ+js7iQF4=",
    "G05B5EkFy578f4UeJPe/dyxooE8pKlByw4xhtU0kiNU/YtZCq69c1Y/C3J6nh2wSf7F/wPLtkOdmXwgL5/vzhiM="
  ]
}
```

Example of genesis chain with power delegated to three signers which of at least 51% need to sign a block.

Genesis chain has always empty `prev_hash` and zero `height` and can be signed with just yet to be delegated power.

Genesis chain is a block generated on a blank sheet, a new chain can be created by anyone.
Creation of a chain should be always done on private channels and should always utilize multisig capability of the chain.

There is one main chain created by operator, coins are distributed and by that distributing signing power.

## Sealing

Chain is not sealed until at least 51% of **all signers** produce a block in their own chain with **witness** operation in it.

## Blocks

Blocks with higher `height` have to always have higher `timestamp` and can never contain zero operations.
