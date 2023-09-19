---
description: SQL table schema for polygon.token_transfers_erc20
---

# polygon.token\_transfers\_erc20

Polygon ERC-20 token transfers.

| Column Name        | Data Type         | Description                                  |
| ------------------ | ----------------- | -------------------------------------------- |
| `token_address`    | CHARACTER VARYING | Address of the token                         |
| `from_address`     | CHARACTER VARYING | Address of the sender                        |
| `to_address`       | CHARACTER VARYING | Address of the receiver                      |
| `value`            | CHARACTER VARYING | Amount of token transferred                  |
| `transaction_hash` | CHARACTER VARYING | Transaction hash                             |
| `log_index`        | BIGINT            | Log index in transaction receipt             |
| `block_timestamp`  | BIGINT            | Block timestamp where the transaction was in |
| `block_number`     | BIGINT            | Block number where the transaction was in    |
| `block_hash`       | CHARACTER VARYING | Block hash where the transaction was in      |
