---
description: SQL table schema for btc.blocks and btc.recent_blocks
---

# btc.blocks

Bitcoin Block headers.

| Column Name         | Data Type         | Description                                                         |
| ------------------- | ----------------- | ------------------------------------------------------------------- |
| `number`            | BIGINT            | Block number                                                        |
| `hash`              | CHARACTER VARYING | Block hash                                                          |
| `size`              | BIGINT            | The size of the block, in bytes                                     |
| `stripped_size`     | BIGINT            | The size of block data in bytes excluding witness data              |
| `weight`            | BIGINT            | Three times the base size plus the total size                       |
| `version`           | BIGINT            | Protocol version specified in block header                          |
| `merkle_root`       | CHARACTER VARYING | The root node of a Merkle tree, where leaves are transaction hashes |
| `timestamp`         | BIGINT            | Timestamp of the block being collated                               |
| `nonce`             | CHARACTER VARYING | Difficulty solution specified in block header                       |
| `bits`              | CHARACTER VARYING | Difficulty threshold specified in block header                      |
| `coinbase_param`    | CHARACTER VARYING | Data specified in the coinbase transaction of this block            |
| `transaction_count` | BIGINT            | Number of transactions in the block                                 |
