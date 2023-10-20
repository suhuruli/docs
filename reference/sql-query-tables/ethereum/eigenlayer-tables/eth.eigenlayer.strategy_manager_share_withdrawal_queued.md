# eth.eigenlayer.strategy\_manager\_share\_withdrawal\_queued

Decoded table for [ShareWithdrawalQueued](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/core/StrategyManager.sol#L62) events from the [StrategyManager](https://etherscan.io/address/0x858646372cc42e1a627fce94aa7a7033e7cf075a) contract on Ethereum mainnet.

Emitted when a new withdrawal occurs on behalf of `depositor`.

| Column Name        | Data Type         | Description                                                                                 |
| ------------------ | ----------------- | ------------------------------------------------------------------------------------------- |
| `depositor`        | CHARACTER VARYING | The staker who is queuing a withdrawal from EigenLayer.                                     |
| `nonce`            | DECIMAL           | The withdrawal's unique identifier (to the depositor).                                      |
| `strategy`         | CHARACTER VARYING | The strategy that `depositor` has queued to withdraw from.                                  |
| `shares`           | DECIMAL           | The number of shares `depositor` has queued to withdraw.                                    |
| `shares_hex`       | CHARACTER VARYING | The number of shares `depositor` has queued to withdraw as a hexadecimal string.            |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction where this event occurred.                                      |
| `log_index`        | BIGINT            | The index of the log event within the Ethereum block.                                       |
| `block_hash`       | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.              |
| `block_timestamp`  | BIGINT            | The timestamp of the block that contains the transaction which contains this event.         |
| `block_number`     | BIGINT            | The block number in the blockchain that contains the transaction which contains this event. |
