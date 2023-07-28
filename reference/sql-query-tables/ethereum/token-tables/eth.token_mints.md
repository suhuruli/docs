---
description: SQL table schema for eth.token_mints and eth.recent_token_mints
---

# eth.token\_mints

Ethereum Token mints from the last 30 minutes, \~128 blocks.

| Colum Name         | Data Type         | Description                                                     |
| ------------------ | ----------------- | --------------------------------------------------------------- |
| `name`             | CHARACTER VARYING | The human-readable name of this token, eg. "AliceInWonderland". |
| `symbol`           | CHARACTER VARYING | The human-readable short symbol of this token, eg. "ALICE".     |
| `token_address`    | CHARACTER VARYING | The address of the contract that defines this token.            |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this mint.                      |
| `value`            | CHARACTER VARYING | The number of tokens transferred.                               |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this transfer occurred.    |
| `block_number`     | BIGINT            | The number of the block in which this transfer occurred.        |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this transfer occurred.     |
