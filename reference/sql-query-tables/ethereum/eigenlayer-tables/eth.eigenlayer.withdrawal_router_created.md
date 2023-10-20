# eth.eigenlayer.withdrawal\_router\_created

Decoded table for [DelayedWithdrawalCreated](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/pods/DelayedWithdrawalRouter.sol#L33) events from the [DelayedWithdrawalRouter](https://etherscan.io/address/0x7fe7e9cc0f274d2435ad5d56d5fa73e47f6a23d8) contract on Ethereum mainnet.

| Column Name        | Data Type         | Description                                                                                        |
| ------------------ | ----------------- | -------------------------------------------------------------------------------------------------- |
| `pod_owner`        | CHARACTER VARYING | The address of the owner of the pod who initiated the withdrawal.                                  |
| `recipient`        | CHARACTER VARYING | The address of the recipient who can claim the withdrawal.                                         |
| `amount_gwei`      | DECIMAL           | The rounded Ether balance of the amount to claim, in gwei.                                         |
| `amount_hex`       | CHARACTER VARYING | The exact, unrounded Ether balance of the amount to claim, in wei. Stored as a hexadecimal string. |
| `index`            | BIGINT            | The total number of withdrawals this pod owner has initiated.                                      |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction where this event occurred.                                             |
| `log_index`        | BIGINT            | The index of the log event within the Ethereum block.                                              |
| `block_hash`       | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.                     |
| `block_timestamp`  | BIGINT            | The timestamp of the block that contains the transaction which contains this event.                |
| `block_number`     | BIGINT            | The block number in the blockchain that contains the transaction which contains this event.        |
