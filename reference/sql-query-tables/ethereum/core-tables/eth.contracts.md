---
description: SQL table schema for eth.contracts
---

# eth.contracts

Ethereum listing of all contracts.

| Column Name          | Data Type         | Description                                                                                 |
| -------------------- | ----------------- | ------------------------------------------------------------------------------------------- |
| `address`            | CHARACTER VARYING | Address of the contract                                                                     |
| `bytecode`           | CHARACTER VARYING | Compiled EVM bytecode of the contract                                                       |
| `function_sighashes` | ANY               | Array of hashes of function signatures defined in the contract.                             |
| `block_number`       | BIGINT            | The block number containing the contract                                                    |
| `block_hash`         | CHARACTER VARYING | The hash of the block containing the contract                                               |
| `block_timestamp`    | BIGINT            | The timestamp of the block containing the contract                                          |
| `is_erc20`           | BOOLEAN           | True if the contract complies with the ERC-20 token standard, False otherwise.              |
| `is_erc721`          | BOOLEAN           | True if the contract complies with the ERC-721 non-fungible token standard False otherwise. |
| `is_erc1155`         | BOOLEAN           | True if the contract complies with the ERC-1155 multi-token standard, False otherwise.      |
| `erc20_confidence`   | DECIMAL           | The confidence that the contract satisfies ERC20 requirements, within \[0, 1].              |
| `erc721_confidence`  | DECIMAL           | The confidence that the contract satisfies ERC721 requirements, within \[0, 1].             |
| `erc1155_confidence` | DECIMAL           | The confidence that the contract satisfies ERC1155 requirements, within \[0, 1].            |
