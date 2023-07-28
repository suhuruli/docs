---
description: SQL table schema for eth.tokens
---

# eth.tokens

Ethereum Token tables ERC-20, ERC-721 and ERC-1155 token contracts.

| Column Name       | Data Type         | Description                                                                                |
| ----------------- | ----------------- | ------------------------------------------------------------------------------------------ |
| `address`         | CHARACTER VARYING | The address of the contract that defines this token.                                       |
| `name`            | CHARACTER VARYING | The human-readable name of this token, eg. "AliceInWonderland".                            |
| `symbol`          | CHARACTER VARYING | The human-readable short symbol of this token, eg. "ALICE".                                |
| `decimals`        | INTEGER           | The number of decimal places that this token uses to represent fixed point values/amounts. |
| `total_supply`    | CHARACTER VARYING | The total number of unique instances of this token.                                        |
| `is_erc20`        | BOOLEAN           | True if Spice considers this token contract to conform to the ERC20 standard.              |
| `is_erc721`       | BOOLEAN           | True if Spice considers this token contract to conform to the ERC721 standard.             |
| `is_erc1155`      | BOOLEAN           | True if Spice considers this token contract to conform to the ERC1155 standard.            |
| `block_number`    | BIGINT            | The number of the block in which this token was first defined.                             |
| `block_timestamp` | BIGINT            | The timestamp of the block in which this token was first defined.                          |
| `block_hash`      | CHARACTER VARYING | The hash of the block in which this token was first defined.                               |
