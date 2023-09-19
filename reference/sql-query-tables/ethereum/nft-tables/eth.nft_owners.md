---
description: SQL table schema for eth.nft_owners
---

# eth.nft\_owners

Ethereum NFT tables tracks the current owner of an NFT.\
This table is mutable; the number of rows within a given time or block range can be different due to changes in NFT ownership.

| Column Name        | Data Type         | Description                                                              |
| ------------------ | ----------------- | ------------------------------------------------------------------------ |
| `token_address`    | CHARACTER VARYING | The contract address of this NFT.                                        |
| `token_id`         | CHARACTER VARYING | The unique, opaque identifier of this specific NFT mint.                 |
| `owner`            | CHARACTER VARYING | The address of the owner of this unique `(token_address, token_id)` NFT. |
| `block_timestamp`  | BIGINT            | The block timestamp when this NFT ownership was validated.               |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this ownership was validated.       |

