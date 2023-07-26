---
description: SQL table schema for btc.transactions and btc.recent_transactions
---

# btc.transactions

Bitcoin Block transactions.

| Column Name       | Data Type         | Description                                                                                                                                  |
| ----------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `hash`            | CHARACTER VARYING | The hash of this transaction                                                                                                                 |
| `size`            | BIGINT            | The size of this transaction in bytes                                                                                                        |
| `virtual_size`    | BIGINT            | The virtual transaction size (differs from size for witness transactions                                                                     |
| `version`         | BIGINT            | Protocol version specified in block which contained this transaction                                                                         |
| `lock_time`       | BIGINT            | Earliest time that miners can include the transaction in their hashing of the Merkle root to attach it in the latest block of the blockchain |
| `block_hash`      | CHARACTER VARYING | Hash of the block which contains this transaction                                                                                            |
| `block_number`    | BIGINT            | Number of the block which contains this transaction                                                                                          |
| `block_timestamp` | BIGINT            | Timestamp of the block which contains this transaction                                                                                       |
| `input_count`     | BIGINT            | The number of inputs in the transaction                                                                                                      |
| `output_count`    | BIGINT            | The number of outputs in the transaction                                                                                                     |
| `input_value`     | DECIMAL           | Total value of inputs in the transaction                                                                                                     |
| `output_value`    | DECIMAL           | Total value of outputs in the transaction                                                                                                    |
| `is_coinbase`     | BOOLEAN           | True if this transaction is a coinbase transaction                                                                                           |
| `fee`             | DECIMAL           | The fee paid by this transaction                                                                                                             |
