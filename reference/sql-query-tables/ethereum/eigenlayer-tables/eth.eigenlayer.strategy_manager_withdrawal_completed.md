# eth.eigenlayer.strategy\_manager\_withdrawal\_completed

Decoded table for [WithdrawalCompleted](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/core/StrategyManager.sol#L79) events from the [StrategyManager](https://etherscan.io/address/0x858646372cc42e1a627fce94aa7a7033e7cf075a) contract on Ethereum mainnet.

Emitted when a queued withdrawal is completed.

| Column Name         | Data Type         | Description                                                                                           |
| ------------------- | ----------------- | ----------------------------------------------------------------------------------------------------- |
| `depositor`         | CHARACTER VARYING | The `staker` who queued the withdrawal from EigenLayer.                                               |
| `nonce`             | DECIMAL           | The withdrawal's unique identifier (to the depositor).                                                |
| `withdrawer`        | CHARACTER VARYING | The party specified by `staker` who completed the queued withdrawal and received the withdrawn funds. |
| `withdrawal_root`   | CHARACTER VARYING | A hash of the input data for the withdrawal.                                                          |
| `transaction_hash`  | CHARACTER VARYING | The hash of the transaction where this event occurred.                                                |
| `log_index`         | BIGINT            | The index of the log event within the Ethereum block.                                                 |
| `block_hash`        | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.                        |
| `block_timestamp`   | BIGINT            | The timestamp of the block that contains the transaction which contains this event.                   |
| `block_number`      | BIGINT            | The block number in the blockchain that contains the transaction which contains this event.           |
| `strategy`          | CHARACTER VARYING | The contract address of the strategy that has a completed withdrawal.                                 |
| `shares`            | DECIMAL           | The number of shares withdrawn                                                                        |
| `shares_hex`        | CHARACTER VARYING | The number of shares withdrawn as a hexadecimal string.                                               |
| `caller`            | CHARACTER VARYING | The address of the caller on the StrategyManager contract                                             |
| `token`             | CHARACTER VARYING | The token that `depositor` deposited.                                                                 |
| `token_amount`      | DECIMAL           | The number of tokens deposited                                                                        |
| `token_amount_hex`  | CHARACTER VARYING | The number of tokens deposited as a hexadecimal string.                                               |
| `receive_as_tokens` | BOOLEAN           | Whether the withdrawer has flagged to receive the funds as tokens                                     |
