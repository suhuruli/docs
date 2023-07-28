---
description: SQL table schema for eth.tokens_erc1155
---

# eth.tokens\_erc1155

Ethereum Token tables ERC-1155 token contracts.

| Column Name       | Data Type         | Description                                                       |
| ----------------- | ----------------- | ----------------------------------------------------------------- |
| `address`         | CHARACTER VARYING | The address of the contract that defines this token.              |
| `name`            | CHARACTER VARYING | The human-readable name of this token, eg. "AliceInWonderland".   |
| `symbol`          | CHARACTER VARYING | The human-readable short symbol of this token, eg. "ALICE".       |
| `block_number`    | BIGINT            | The number of the block in which this token was first defined.    |
| `block_timestamp` | BIGINT            | The timestamp of the block in which this token was first defined. |
| `block_hash`      | CHARACTER VARYING | The hash of the block in which this token was first defined.      |
