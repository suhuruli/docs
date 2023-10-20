# eth.eigenlayer.strategy\_manager\_deposits

Decoded table for [Deposit](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/core/StrategyManager.sol#L51) events from the [StrategyManager](https://etherscan.io/address/0x858646372cc42e1a627fce94aa7a7033e7cf075a) contract on Ethereum mainnet.

Emitted when a new deposit occurs on behalf of `depositor`.

| Column Name        | Data Type         | Description                                                                                  |
| ------------------ | ----------------- | -------------------------------------------------------------------------------------------- |
| `depositor`        | CHARACTER VARYING | The address of the staker who is depositing funds into EigenLayer.                           |
| `token`            | CHARACTER VARYING | The token that `depositor` deposited.                                                        |
| `strategy`         | CHARACTER VARYING | The strategy that `depositor` has deposited into.                                            |
| `shares`           | DECIMAL           | The number of new shares `depositor` has been granted in `strategy`.                         |
| `shares_hex`       | CHARACTER VARYING | The number of new shares `depositor` has been granted in `strategy` as a hexadecimal string. |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction where this event occurred.                                       |
| `log_index`        | BIGINT            | The index of the log event within the Ethereum block.                                        |
| `block_hash`       | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.               |
| `block_timestamp`  | BIGINT            | The timestamp of the block that contains the transaction which contains this event.          |
| `block_number`     | BIGINT            | The block number in the blockchain that contains the transaction which contains this event.  |
| `caller`           | CHARACTER VARYING | The address of the caller on the StrategyManager contract                                    |
| `token_amount`     | DECIMAL           | The number of tokens deposited                                                               |
| `token_amount_hex` | CHARACTER VARYING | The number of tokens deposited as a hexadecimal string.                                      |
