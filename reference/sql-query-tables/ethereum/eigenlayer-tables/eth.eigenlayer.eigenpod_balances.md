# eth.eigenlayer.eigenpod\_balances

This table has a row for each wallet balance change for all eigenpods. It's possible for a row to have a `balance_delta` of 0, if the balance didn't change between blocks but our logic for detecting balance changes still triggered.

| Column Name        | Data Type         | Description                                                                                  |
| ------------------ | ----------------- | -------------------------------------------------------------------------------------------- |
| `eigenpod_address` | CHARACTER VARYING | The smart contract address of the eigenpod.                                                  |
| `balance_gwei`     | DECIMAL           | The rounded Ether balance of this eigenpod, in gwei.                                         |
| `balance_hex`      | CHARACTER VARYING | The exact, unrounded Ether balance of this eigenpod, in wei. Stored as a hexadecimal string. |
| `balance_delta`    | DECIMAL           | The change in balance (in gwei) from the previous block. Can be 0.                           |
| `block_timestamp`  | BIGINT            | The timestamp of the block when this eigenpod had this balance.                              |
| `block_number`     | BIGINT            | The block number when this eigenpod had this balance.                                        |
| `block_hash`       | CHARACTER VARYING | The hash of the block when this eigenpod had this balance.                                   |
