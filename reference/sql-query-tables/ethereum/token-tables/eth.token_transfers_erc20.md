---
description: SQL table schema for eth.token_transfers_erc20
---

# eth.token\_transfers\_erc20

Ethereum Token tables ERC-20 token transfers.

| Column Name        | Data Type         | Description                                                  |
| ------------------ | ----------------- | ------------------------------------------------------------ |
| `token_address`    | CHARACTER VARYING | The contract address of the token being transferred.         |
| `from_address`     | CHARACTER VARYING | The address of the sender of this transfer.                  |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this transfer.               |
| `value`            | CHARACTER VARYING | The number of tokens transferred.                            |
| `value_hex`        | CHARACTER VARYING | The value, encoded as a hexadecimal string.                  |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this transfer occurred. |
| `log_index`        | BIGINT            | The index of this transfer within the transaction.           |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this transfer occurred.  |
| `block_number`     | BIGINT            | The number of the block in which this transfer occurred.     |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this transfer occurred.       |
