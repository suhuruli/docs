---
description: SQL table schema for polygon.contracts
---

# polygon.contracts

A listing of all Polygon contracts.

| Column Name          | Data Type         | Description                                        |
| -------------------- | ----------------- | -------------------------------------------------- |
| `address`            | CHARACTER VARYING | Address of the contract                            |
| `bytecode`           | CHARACTER VARYING | Bytecode of the contract                           |
| `function_sighashes` | ANY               | Function signature hashes                          |
| `block_number`       | BIGINT            | Block number where the contract creation was in    |
| `block_hash`         | CHARACTER VARYING | Block hash where the contract creation was in      |
| `block_timestamp`    | BIGINT            | Block timestamp where the contract creation was in |
| `is_erc20`           | BOOLEAN           | Whether this contract is an ERC20 contract         |
| `is_erc721`          | BOOLEAN           | Whether this contract is an ERC721 contract        |
| `is_erc1155`         | BOOLEAN           | Whether this contract is an ERC1155 contract       |
| `erc20_confidence`   | DECIMAL           | Confidence level of being ERC20 contract           |
| `erc721_confidence`  | DECIMAL           | Confidence level of being ERC721 contract          |
| `erc1155_confidence` | DECIMAL           | Confidence level of being ERC1155 contract         |
