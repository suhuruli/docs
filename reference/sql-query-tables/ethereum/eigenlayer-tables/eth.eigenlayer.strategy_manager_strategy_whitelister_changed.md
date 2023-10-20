# eth.eigenlayer.strategy\_manager\_strategy\_whitelister\_changed

Decoded table for [StrategyWhitelisterChanged](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/core/StrategyManager.sol#L82) events from the [StrategyManager](https://etherscan.io/address/0x858646372cc42e1a627fce94aa7a7033e7cf075a) contract on Ethereum mainnet.

Emitted when the `strategyWhitelister` is changed.

| Column Name        | Data Type         | Description                                                                                 |
| ------------------ | ----------------- | ------------------------------------------------------------------------------------------- |
| `previous_address` | CHARACTER VARYING | The previous address of the strategy whitelister.                                           |
| `new_address`      | CHARACTER VARYING | The new address of the strategy whitelister.                                                |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction where this event occurred.                                      |
| `log_index`        | BIGINT            | The index of the log event within the Ethereum block.                                       |
| `block_hash`       | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.              |
| `block_timestamp`  | BIGINT            | The timestamp of the block that contains the transaction which contains this event.         |
| `block_number`     | BIGINT            | The block number in the blockchain that contains the transaction which contains this event. |
