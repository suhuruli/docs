# eth.eigenlayer.withdrawal\_recipient\_balances

This table has a row that contains the current Ether balance on each block for each recipient of an eigenpod withdrawal from the DelayedWithdrawalRouter.

| Column Name       | Data Type         | Description                                                                                            |
| ----------------- | ----------------- | ------------------------------------------------------------------------------------------------------ |
| `address`         | CHARACTER VARYING | The address of the recipient                                                                           |
| `balance_gwei`    | DECIMAL           | The rounded Ether balance of the recipient's wallet, in gwei.                                          |
| `balance_hex`     | CHARACTER VARYING | The exact, unrounded Ether balance of this recipient's wallet, in wei. Stored as a hexadecimal string. |
| `block_timestamp` | BIGINT            | The timestamp of the block when the recipient's wallet had this balance.                               |
| `block_number`    | BIGINT            | The block number when the recipient's wallet had this balance.                                         |
| `block_hash`      | CHARACTER VARYING | The hash of the block when the recipient's wallet had this balance.                                    |
