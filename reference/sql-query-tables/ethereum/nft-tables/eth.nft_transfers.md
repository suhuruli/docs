---
description: SQL table schema for eth.nft_transfers
---

# eth.nft\_transfers

All Ethereum erc721 contracts & subset of erc1155 contracts that contain NFTs.

| Column Name        | Data Type         | Description                                                               |
| ------------------ | ----------------- | ------------------------------------------------------------------------- |
| `token_address`    | CHARACTER VARYING | The contract address of this NFT.                                         |
| `from_address`     | CHARACTER VARYING | The address of the sender of this NFT.                                    |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this NFT.                                 |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this transfer occurred.              |
| `token_id`         | CHARACTER VARYING | The unique, opaque identifier of the specific NFT mint being transferred. |
| `block_number`     | BIGINT            | The block number when this NFT transfer occurred.                         |
| `block_timestamp`  | BIGINT            | The block timestamp when this NFT transfer occurred.                      |
| `block_hash`       | CHARACTER VARYING | The hash of the block when this NFT transfer occurred.                    |
