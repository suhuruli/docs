---
description: SQL table schema for eth.tokens_erc20
---

# eth.tokens\_erc20

Ethereum Token tables ERC-20 token contracts.

| Column Name       | Data Type         | Description                                                                                |
| ----------------- | ----------------- | ------------------------------------------------------------------------------------------ |
| `address`         | CHARACTER VARYING | The address of the contract that defines this token.                                       |
| `name`            | CHARACTER VARYING | The human-readable name of this token, eg. "AliceInWonderland".                            |
| `symbol`          | CHARACTER VARYING | The human-readable short symbol of this token, eg. "ALICE".                                |
| `decimals`        | INTEGER           | The number of decimal places that this token uses to represent fixed point values/amounts. |
| `total_supply`    | CHARACTER VARYING | The total number of unique instances of this token.                                        |
| `block_number`    | BIGINT            | The number of the block in which this token was first defined.                             |
| `block_timestamp` | BIGINT            | The timestamp of the block in which this token was first defined.                          |
| `block_hash`      | CHARACTER VARYING | The hash of the block in which this token was first defined.                               |
