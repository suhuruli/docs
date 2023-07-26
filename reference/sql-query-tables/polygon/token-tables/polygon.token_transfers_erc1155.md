---
description: SQL table schema for polygon.token_transfers_erc1155
---

# polygon.token\_transfers\_erc1155

Polygon ERC-1155 token transfers.

| Column Name        | Data Type         | Description                                    |
| ------------------ | ----------------- | ---------------------------------------------- |
| `token_address`    | CHARACTER VARYING | Address of the token                           |
| `operator`         | CHARACTER VARYING | Address which initiated the transfer           |
| `from_address`     | CHARACTER VARYING | Address of the sender                          |
| `to_address`       | CHARACTER VARYING | Address of the receiver                        |
| `token_id`         | CHARACTER VARYING | Token id of the token transferred              |
| `value`            | CHARACTER VARYING | Amount of token transferred                    |
| `value_hex`        | CHARACTER VARYING | Amount of token transferred in hexadecimal     |
| `transaction_hash` | CHARACTER VARYING | Transaction hash                               |
| `log_index`        | BIGINT            | Log index in transaction receipt               |
| `block_timestamp`  | BIGINT            | Block timestamp where the transaction was in   |
| `block_number`     | BIGINT            | Block number where the transaction was in      |
| `block_hash`       | CHARACTER VARYING | Block hash where the transaction was in        |
| `batch_index`      | BIGINT            | Index of this token transfer in transfer batch |
