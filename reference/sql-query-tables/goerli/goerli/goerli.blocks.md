---
description: SQL table schema for goerli.blocks and goerli.recent_blocks
---

# goerli.blocks

Goerli Block headers.

| Column Name         | Data Type         |
| ------------------- | ----------------- |
| `number`            | BIGINT            |
| `hash`              | CHARACTER VARYING |
| `parent_hash`       | CHARACTER VARYING |
| `nonce`             | CHARACTER VARYING |
| `sha3_uncles`       | CHARACTER VARYING |
| `logs_bloom`        | CHARACTER VARYING |
| `transactions_root` | CHARACTER VARYING |
| `state_root`        | CHARACTER VARYING |
| `receipts_root`     | CHARACTER VARYING |
| `miner`             | CHARACTER VARYING |
| `difficulty`        | DECIMAL           |
| `total_difficulty`  | DECIMAL           |
| `size`              | BIGINT            |
| `extra_data`        | CHARACTER VARYING |
| `gas_limit`         | BIGINT            |
| `gas_used`          | BIGINT            |
| `timestamp`         | BIGINT            |
| `transaction_count` | BIGINT            |
| `base_fee_per_gas`  | BIGINT            |
| `withdrawals_root`  | CHARACTER VARYING |
| `withdrawal_count`  | BIGINT            |
