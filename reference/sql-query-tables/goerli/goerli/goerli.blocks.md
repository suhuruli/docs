---
description: SQL table schema for goerli.blocks and goerli.recent_blocks
---

# goerli.blocks

Goerli Block headers.

| Column Name         | Data Type         | Description                                        |
| ------------------- | ----------------- | -------------------------------------------------- |
| `number`            | BIGINT            | The block number                                   |
| `hash`              | CHARACTER VARYING | Block hash                                         |
| `parent_hash`       | CHARACTER VARYING | Parent block's hash                                |
| `nonce`             | CHARACTER VARYING | Hash of the generated proof of work                |
| `sha3_uncles`       | CHARACTER VARYING | SHA3 of the uncles data in the block               |
| `logs_bloom`        | CHARACTER VARYING | The bloom filter for the logs of the block         |
| `transactions_root` | CHARACTER VARYING | The root for the transaction trie of the block     |
| `state_root`        | CHARACTER VARYING | The root for the final state trie of the block     |
| `receipts_root`     | CHARACTER VARYING | The root for the receipts trie of the block        |
| `miner`             | CHARACTER VARYING | The miner address rewarded for this block          |
| `difficulty`        | DECIMAL           | The difficulty of the block, as an integer         |
| `total_difficulty`  | DECIMAL           | The total difficulty of the chain until this block |
| `size`              | BIGINT            | The size of the block, in bytes                    |
| `extra_data`        | CHARACTER VARYING | Extra data pertaining to the block                 |
| `gas_limit`         | BIGINT            | The maximum gas for this block                     |
| `gas_used`          | BIGINT            | The net gas used in transactions in this block     |
| `timestamp`         | BIGINT            | Timestamp of the block being collated              |
| `transaction_count` | BIGINT            | The number of transactions in the block            |
| `base_fee_per_gas`  | BIGINT            | The base fee per gas burnt                         |
| `withdrawals_root`  | CHARACTER VARYING | The root hash of the withdrawals in the payload    |
| `withdrawal_count`  | BIGINT            | The number of withdrawals in the payload           |

