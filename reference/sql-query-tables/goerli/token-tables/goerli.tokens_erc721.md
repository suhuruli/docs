---
description: SQL table schema for goerli.tokens_erc721
---

# goerli.tokens\_erc721

Goerli ERC-721 token contracts.

| Column Name       | Data Type         | Description                                                       |
| ----------------- | ----------------- | ----------------------------------------------------------------- |
| `address`         | CHARACTER VARYING | The address of the contract that defines this token.              |
| `name`            | CHARACTER VARYING | The human-readable name of this token, eg. "AliceInWonderland".   |
| `symbol`          | CHARACTER VARYING | The human-readable short symbol of this token, eg. "ALICE".       |
| `total_supply`    | CHARACTER VARYING | The total number of unique instances of this token.               |
| `block_number`    | BIGINT            | The number of the block in which this token was first defined.    |
| `block_timestamp` | BIGINT            | The timestamp of the block in which this token was first defined. |
| `block_hash`      | CHARACTER VARYING | The hash of the block in which this token was first defined.      |
