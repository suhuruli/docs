# eth.eigenlayer.strategy\_manager\_added\_to\_deposit\_whitelist

Decoded table for [StrategyAddedToDepositWhitelist](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/core/StrategyManager.sol#L85) events from the [StrategyManager](https://etherscan.io/address/0x858646372cc42e1a627fce94aa7a7033e7cf075a) contract on Ethereum mainnet.

Emitted when a strategy is added to the approved list of strategies for deposit.

| Column Name        | Data Type         | Description                                                                                 |
| ------------------ | ----------------- | ------------------------------------------------------------------------------------------- |
| `strategy`         | CHARACTER VARYING | The contract address of the strategy that was added to the deposit whitelist.               |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction where this event occurred.                                      |
| `log_index`        | BIGINT            | The index of the log event within the Ethereum block.                                       |
| `block_hash`       | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.              |
| `block_timestamp`  | BIGINT            | The timestamp of the block that contains the transaction which contains this event.         |
| `block_number`     | BIGINT            | The block number in the blockchain that contains the transaction which contains this event. |
