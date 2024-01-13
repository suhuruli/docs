---
description: SQL table schema for holesky.tokens_erc1155
---

# holesky.tokens\_erc1155

Holesky ERC-1155 token contracts.

| Column Name       | Data Type         | Description                                                       |
| ----------------- | ----------------- | ----------------------------------------------------------------- |
| `address`         | CHARACTER VARYING | The address of the contract that defines this token.              |
| `name`            | CHARACTER VARYING | The human-readable name of this token, eg. "AliceInWonderland".   |
| `symbol`          | CHARACTER VARYING | The human-readable short symbol of this token, eg. "ALICE".       |
| `block_number`    | BIGINT            | The number of the block in which this token was first defined.    |
| `block_timestamp` | BIGINT            | The timestamp of the block in which this token was first defined. |
| `block_hash`      | CHARACTER VARYING | The hash of the block in which this token was first defined.      |
