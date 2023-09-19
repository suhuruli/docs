---
description: SQL table schema for eth.nft_contracts
---

# eth.nft\_contracts

All Ethereum erc721 contracts & subset of erc1155 contracts that contain NFTs.

| Column Name  | Data Type         | Description                                                                     |
| ------------ | ----------------- | ------------------------------------------------------------------------------- |
| `address`    | CHARACTER VARYING | The contract address of this NFT.                                               |
| `is_erc721`  | BOOLEAN           | True if Spice considers this token contract to conform to the ERC721 standard.  |
| `is_erc1155` | BOOLEAN           | True if Spice considers this token contract to conform to the ERC1155 standard. |
