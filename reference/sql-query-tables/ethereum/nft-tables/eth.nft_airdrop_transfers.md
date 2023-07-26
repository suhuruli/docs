---
description: SQL table schema for eth.nft_airdrop_transfers
---

# eth.nft\_airdrop\_transfers

Ethereum Airdrops of NFTs.

| Column Name        | Data Type         | Description                                                                                         |
| ------------------ | ----------------- | --------------------------------------------------------------------------------------------------- |
| `token_address`    | CHARACTER VARYING | The contract address of this NFT.                                                                   |
| `token_id`         | CHARACTER VARYING | The unique, opaque identifier of the specific NFT mint being transferred.                           |
| `tx_from_address`  | CHARACTER VARYING | The address of the initiator of the airdrop transfer.                                               |
| `tx_value`         | DECIMAL           | The [value on the transaction](../core-tables/eth.transactions.md) in which this transfer occurred. |
| `from_address`     | CHARACTER VARYING | The address of the sender of this NFT.                                                              |
| `to_address`       | CHARACTER VARYING | The address of the recipient of this NFT.                                                           |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this transfer occurred.                                        |
| `block_number`     | BIGINT            | The block number when this NFT transfer occurred.                                                   |
| `block_timestamp`  | BIGINT            | The block timestamp when this NFT transfer occurred.                                                |
| `block_hash`       | CHARACTER VARYING | The hash of the block when this NFT transfer occurred.                                              |
