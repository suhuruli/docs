---
description: >-
  SQL table schema for eth.uniswap_v3.event_flashes and
  eth.uniswap_v3.recent_event_flashes
---

# eth.uniswap\_v3.event\_flashes

Ethereum Uniswap-V3 flash events.

| Column Name        | Data Type         | Description                                              |
| ------------------ | ----------------- | -------------------------------------------------------- |
| `address`          | CHARACTER VARYING | The address of the contract that defines this pool.      |
| `log_index`        | BIGINT            | The index of this flash loan in the block.               |
| `amount0`          | CHARACTER VARYING | The amount of the first token being loaned.              |
| `amount1`          | CHARACTER VARYING | The amount of the second token being loaned.             |
| `paid0`            | CHARACTER VARYING | The amount of the first token being paid.                |
| `paid1`            | CHARACTER VARYING | The amount of the second token being paid.               |
| `sender`           | CHARACTER VARYING | The initiator of this flash loan.                        |
| `recipient`        | CHARACTER VARYING | The recipient of this flash loan.                        |
| `transaction_hash` | CHARACTER VARYING | The hash of the transaction in which this loan occurred. |
| `block_timestamp`  | BIGINT            | The timestamp of the block in which this loan occurred.  |
| `block_number`     | BIGINT            | The number of the block in which this loan occurred.     |
| `block_hash`       | CHARACTER VARYING | The hash of the block in which this loan occurred.       |
