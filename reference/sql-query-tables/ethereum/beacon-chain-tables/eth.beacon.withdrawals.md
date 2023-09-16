---
description: SQL table schema for eth.beacon.withdrawals and eth.beacon.recent_withdrawals
---

# eth.beacon.withdrawals



Ethereum Beacon withdrawals of ETH from the beacon chain to the main Ethereum chain. More [details](https://ethereum.org/en/staking/withdrawals/).

| Column Name        | Data Type         | Description                                              |
| ------------------ | ----------------- | -------------------------------------------------------- |
| `block_slot`       | DOUBLE            | Index of slot in the block the slashing was processed.   |
| `block_root`       | CHARACTER VARYING | Root hash of block the slashing was processed.           |
| `block_timestamp`  | BIGINT            | Timestamp of the block the slashing was processed.       |
| `withdrawal_index` | DOUBLE            | The index of the withdrawal within the block.            |
| `validator_index`  | DOUBLE            | The index for the validator who made the change request. |
| `address`          | CHARACTER VARYING | The address that the ETH was withdrawn to.               |
| `amount`           | DOUBLE            | Amount of ETH withdrawn (in gwei).                       |
