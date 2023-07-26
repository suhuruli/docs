---
description: SQL table schema for goerli.wallet_balances
---

# goerli.wallet\_balances

| Column            | Data Type         | Description                                                                                    |
| ----------------- | ----------------- | ---------------------------------------------------------------------------------------------- |
| `address`         | CHARACTER VARYING | The wallet address that contains this Ether balance.                                           |
| `balance_gwei`    | DECIMAL           | The rounded Ether balance of this wallet, in **gwei**. Overflows are recorded as -1.           |
| `balance_hex`     | CHARACTER VARYING | The exact, unrounded Ether balance of this wallet, in **wei**. Stored as a hexadecimal string. |
| `balance_usd`     | DECIMAL           | The approximate USD balance of this wallet at this block.                                      |
| `block_timestamp` | BIGINT            | The timestamp of the block when this wallet had this balance.                                  |
| `block_number`    | BIGINT            | The block number when this wallet had this balance.                                            |
| `block_hash`      | CHARACTER VARYING | The hash of the block when this wallet had this balance.                                       |
