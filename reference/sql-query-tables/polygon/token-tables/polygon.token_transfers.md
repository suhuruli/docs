---
description: SQL table schema for polygon.token_transfers
---

# polygon.token\_transfers

Polygon ERC-20, ERC-721, and ERC-1155 token transfers.

| Column Name        | Data Type         | Description                                  |
| ------------------ | ----------------- | -------------------------------------------- |
| `token_address`    | CHARACTER VARYING | Address of the token                         |
| `from_address`     | CHARACTER VARYING | Address of the sender                        |
| `to_address`       | CHARACTER VARYING | Address of the receiver                      |
| `token_id`         | CHARACTER VARYING | Token id of the token transferred            |
| `token_standard`   | CHARACTER VARYING | One of erc20, erc721, erc1155                |
| `value`            | CHARACTER VARYING | Amount of token transferred                  |
| `transaction_hash` | CHARACTER VARYING | Transaction hash                             |
| `log_index`        | BIGINT            | Log index in transaction receipt             |
| `block_timestamp`  | BIGINT            | Block timestamp where the transaction was in |
| `block_number`     | BIGINT            | Block number where the transaction was in    |
| `block_hash`       | CHARACTER VARYING | Block hash where the transaction was in      |
| `batch_index`      | BIGINT            | Batch index of token transfer transaction    |
