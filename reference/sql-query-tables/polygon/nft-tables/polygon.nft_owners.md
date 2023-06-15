---
description: SQL table schema for polygon.nft_owners
---

# polygon.nft\_owners

Tracks the current owner of an NFT. This table is mutable; the number of rows within a given time or block range can be different due to changes in NFT ownership.

| Column Name        | Data Type         |
| ------------------ | ----------------- |
| `token_address`    | CHARACTER VARYING |
| `token_id`         | CHARACTER VARYING |
| `owner`            | CHARACTER VARYING |
| `block_timestamp`  | BIGINT            |
| `transaction_hash` | CHARACTER VARYING |
