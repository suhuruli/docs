---
description: SQL table schema for eth.recent_token_transfers
---

# eth.recent\_token\_transfers

Ethereum Token transfers from the last 30 minutes, \~128 blocks.

| Column Name        | Data Type         | Description                                                          |
| ------------------ | ----------------- | -------------------------------------------------------------------- |
| `token_address`    | CHARACTER VARYING | The contract address of the token being transferred.                 |
| `from_address`     | CHARACTER VARYING | The address of the sender of this transfer.                          |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this transfer.                       |
| `token_id`         | CHARACTER VARYING | The unique instance id of the specific token mint being transferred. |
| `token_standard`   | CHARACTER VARYING | The primary ERC standard this token implements.                      |
| `value`            | CHARACTER VARYING | The number of tokens transferred.                                    |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this transfer occurred.         |
| `log_index`        | BIGINT            | The index of this transfer within the transaction.                   |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this transfer occurred.          |
| `block_number`     | BIGINT            | The number of the block in which this transfer occurred.             |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this transfer occurred.               |
| `batch_index`      | BIGINT            | The batch number of this transfer, for large batched transfers.      |
