# eth.eigenlayer.withdrawal\_router\_balances

This table has a row that contains the current Ether balance on each block for the [Ethereum mainnet DelayedWithdrawalRouter](https://etherscan.io/address/0x7fe7e9cc0f274d2435ad5d56d5fa73e47f6a23d8).

| Column Name       | Data Type         | Description                                                                                                    |
| ----------------- | ----------------- | -------------------------------------------------------------------------------------------------------------- |
| `balance_gwei`    | DECIMAL           | The rounded Ether balance of the withdrawal router contract, in gwei.                                          |
| `balance_hex`     | CHARACTER VARYING | The exact, unrounded Ether balance of this withdrawal router contract, in wei. Stored as a hexadecimal string. |
| `balance_delta`   | DECIMAL           | The change in balance (in gwei) from the previous block. Can be 0.                                             |
| `block_timestamp` | BIGINT            | The timestamp of the block when the withdrawal router contract had this balance.                               |
| `block_number`    | BIGINT            | The block number when the withdrawal router contract had this balance.                                         |
| `block_hash`      | CHARACTER VARYING | The hash of the block when the withdrawal router contract had this balance.                                    |
