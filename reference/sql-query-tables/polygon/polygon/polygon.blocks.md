---
description: SQL table schema for polygon.blocks and polygon.recent_blocks
---

# polygon.blocks

Polygon Block headers.

| Column Name         | Data Type         | Description                                                          |
| ------------------- | ----------------- | -------------------------------------------------------------------- |
| `number`            | BIGINT            | The number of the current block                                      |
| `hash`              | CHARACTER VARYING | Hash of the current block                                            |
| `parent_hash`       | CHARACTER VARYING | Hash of the parent block                                             |
| `nonce`             | CHARACTER VARYING | Hash of the generated proof of work                                  |
| `sha3_uncles`       | CHARACTER VARYING | SHA3 of the uncles data in the block                                 |
| `logs_bloom`        | CHARACTER VARYING | The bloom filter for the block event logs                            |
| `transactions_root` | CHARACTER VARYING | The root of the transaction trie of the block                        |
| `state_root`        | CHARACTER VARYING | The root of the final state trie of the block                        |
| `receipts_root`     | CHARACTER VARYING | The root of the receipts trie of the block.                          |
| `miner`             | CHARACTER VARYING | The address of the beneficiary to whom the mining rewards were given |
| `difficulty`        | DECIMAL           | The difficulty for this block                                        |
| `total_difficulty`  | DECIMAL           | The total difficulty of the chain until this block                   |
| `size`              | BIGINT            | The size of this block in bytes                                      |
| `extra_data`        | CHARACTER VARYING | Arbitrary additional data as raw bytes                               |
| `gas_limit`         | BIGINT            | The maximum gas allowed in this block                                |
| `gas_used`          | BIGINT            | The total gas used by transactions in the block                      |
| `timestamp`         | BIGINT            | Unix timestamp for when the block was collated                       |
| `transaction_count` | BIGINT            | Transaction counts of the block                                      |
