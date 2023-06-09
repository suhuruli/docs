---
description: SQL table schema for btc.blocks and btc.recent_blocks
---

# btc.blocks

| Column Name         | Data Type         |
| ------------------- | ----------------- |
| `number`            | BIGINT            |
| `hash`              | CHARACTER VARYING |
| `size`              | BIGINT            |
| `stripped_size`     | BIGINT            |
| `weight`            | BIGINT            |
| `version`           | BIGINT            |
| `merkle_root`       | CHARACTER VARYING |
| `timestamp`         | BIGINT            |
| `nonce`             | CHARACTER VARYING |
| `bits`              | CHARACTER VARYING |
| `coinbase_param`    | CHARACTER VARYING |
| `transaction_count` | BIGINT            |
