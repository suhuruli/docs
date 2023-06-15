---
description: SQL table schema for eth.recent_nft_transfers
---

# eth.recent\_nft\_transfers

Ethereum transfers of NFTs from the last 30 minutes, \~128 blocks.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `from_address`     | CHARACTER VARYING |
| `to_address`       | CHARACTER VARYING |
| `transaction_hash` | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `block_number`     | BIGINT            |
| `block_timestamp`  | BIGINT            |
| `block_hash`       | CHARACTER VARYING |
