# eth.eigenlayer.strategy\_manager\_withdrawal\_delay\_blocks\_set

Decoded table for [WithdrawalDelayBlocksSet](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/core/StrategyManager.sol#L91) events from the [StrategyManager](https://etherscan.io/address/0x858646372cc42e1a627fce94aa7a7033e7cf075a) contract on Ethereum mainnet.

Emitted when the `withdrawalDelayBlocks` variable is modified from `previousValue` to `newValue`.

| Column Name          | Data Type         | Description                                                                                 |
| -------------------- | ----------------- | ------------------------------------------------------------------------------------------- |
| `previous_value`     | DECIMAL           | The previous value of `withdrawalDelayBlocks`.                                              |
| `previous_value_hex` | CHARACTER VARYING | The previous value of `withdrawalDelayBlocks` as a hexadecimal string.                      |
| `new_value`          | DECIMAL           | The new value of `withdrawalDelayBlocks`.                                                   |
| `new_value_hex`      | CHARACTER VARYING | The new value of `withdrawalDelayBlocks` as a hexadecimal string.                           |
| `transaction_hash`   | CHARACTER VARYING | The hash of the transaction where this event occurred.                                      |
| `log_index`          | BIGINT            | The index of the log event within the Ethereum block.                                       |
| `block_hash`         | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.              |
| `block_timestamp`    | BIGINT            | The timestamp of the block that contains the transaction which contains this event.         |
| `block_number`       | BIGINT            | The block number in the blockchain that contains the transaction which contains this event. |
