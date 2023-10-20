# eth.eigenlayer.withdrawal\_router\_claimed

Decoded table for [DelayedWithdrawalClaimed](https://github.com/Layr-Labs/eigenlayer-contracts/blob/e80a45c5595dd7d2e31e06c021bad2ca7db0abc7/src/contracts/pods/DelayedWithdrawalRouter.sol#L36C11-L36C36) events from the [DelayedWithdrawalRouter](https://etherscan.io/address/0x7fe7e9cc0f274d2435ad5d56d5fa73e47f6a23d8) contract on Ethereum mainnet.

| Column Name                     | Data Type         | Description                                                                                       |
| ------------------------------- | ----------------- | ------------------------------------------------------------------------------------------------- |
| `recipient`                     | CHARACTER VARYING | The address of the recipient who claimed the withdrawal.                                          |
| `amount_claimed_gwei`           | DECIMAL           | The rounded Ether balance of the amount claimed, in gwei.                                         |
| `amount_claimed_hex`            | CHARACTER VARYING | The exact, unrounded Ether balance of the amount claimed, in wei. Stored as a hexadecimal string. |
| `delayed_withdrawals_completed` | BIGINT            | The total number of completed withdrawals this recipient has claimed.                             |
| `transaction_hash`              | CHARACTER VARYING | The hash of the transaction where this event occurred.                                            |
| `log_index`                     | BIGINT            | The index of the log event within the Ethereum block.                                             |
| `block_hash`                    | CHARACTER VARYING | The hash of the block that contains the transaction which contains this event.                    |
| `block_timestamp`               | BIGINT            | The timestamp of the block that contains the transaction which contains this event.               |
| `block_number`                  | BIGINT            | The block number in the blockchain that contains the transaction which contains this event.       |
