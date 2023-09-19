---
description: SQL table schema for polygon.recent_token_transfers
---

# polygon.recent\_token\_transfers

Polygon Token transfers from the last 30 minutes, \~128 blocks.

| Column Name        | Data Type         | Description                                       |
| ------------------ | ----------------- | ------------------------------------------------- |
| `token_address`    | CHARACTER VARYING | Address of the token                              |
| `from_address`     | CHARACTER VARYING | Address of the sender                             |
| `to_address`       | CHARACTER VARYING | Address of the receiver                           |
| `token_id`         | CHARACTER VARYING | Token id of the token transferred                 |
| `token_standard`   | CHARACTER VARYING | One of erc20, erc721, erc1155                     |
| `value`            | CHARACTER VARYING | Amount of token transferred                       |
| `value_hex`        | CHARACTER VARYING | Amount of token transferred in hexadecimal        |
| `transaction_hash` | CHARACTER VARYING | Transaction hash                                  |
| `log_index`        | BIGINT            | Log index in transaction receipt                  |
| `block_timestamp`  | BIGINT            | Block timestamp where the transaction was in      |
| `block_number`     | BIGINT            | Block number where the transaction was in         |
| `block_hash`       | CHARACTER VARYING | Block hash where the transaction was in           |
| `batch_index`      | BIGINT            | Index of ERC1155 token transfer in transfer batch |
