---
description: SQL table schema for eth.token_transfers_erc721
---

# eth.token\_transfers\_erc721

Ethereum Token tables ERC-721 token transfers (NFTs).

| Column Name        | Data Type         | Description                                                          |
| ------------------ | ----------------- | -------------------------------------------------------------------- |
| `token_address`    | CHARACTER VARYING | The contract address of the token being transferred.                 |
| `from_address`     | CHARACTER VARYING | The address of the sender of this transfer.                          |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this transfer.                       |
| `token_id`         | CHARACTER VARYING | The unique instance id of the specific token mint being transferred. |
| `value`            | CHARACTER VARYING | The number of tokens transferred.                                    |
| `value_hex`        | CHARACTER VARYING | The value, encoded as a hexadecimal string.                          |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this transfer occurred.         |
| `log_index`        | BIGINT            | The index of this transfer within the transaction.                   |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this transfer occurred.          |
| `block_number`     | BIGINT            | The number of the block in which this transfer occurred.             |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this transfer occurred.               |
