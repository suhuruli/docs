---
description: Ethereum EigenLayer tables available to query via SQL
---

# EigenLayer Tables

Learn about [EigenLayer](https://www.eigenlayer.xyz/) and read the [whitepaper](https://2039955362-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPy2Kmkwju3mPSo9jrKKt%2Fuploads%2F2dCfPgItRfQbX25KriQv%2Fwhitepaper.pdf?alt=media\&token=d4d94480-3f01-4e63-bc92-a0658ea37aab).

#### Ethereum EigenLayer tables available to query

| Name     | Description  |
| -------------------------- | -------- |
| `eth.eigenlayer.eigenpods`           | All Eigenpods                                                             |
| `eth.eigenlayer.eigenpod_validators` | All Eigenpod Validators                                                   |
| `eth.eigenlayer.eigenpod_balances`   | Eigenpod ETH wallet changed balances including the delta from last block  |
| `eth.eigenlayer.withdrawal_router`            | Withdrawal Router ETH wallet balances including the delta from last block |
| `eth.eigenlayer.strategy_manager_added_to_deposit_whitelist`     | StrategyManager event for when a strategy is added to the approved list of strategies for deposit |
| `eth.eigenlayer.strategy_manager_deposits`                       | StrategyManager event for when a new deposit occurs on behalf of `depositor` |
| `eth.eigenlayer.strategy_manager_removed_from_deposit_whitelist` | StrategyManager event for when a strategy is removed from the approved list of strategies for deposit |
| `eth.eigenlayer.strategy_manager_share_withdrawal_queued`        | StrategyManager event for when a new withdrawal occurs on behalf of `depositor` |
| `eth.eigenlayer.strategy_manager_strategy_whitelister_changed`   | StrategyManager event for when the `strategyWhitelister` is changed |
| `eth.eigenlayer.strategy_manager_withdrawal_completed`           | StrategyManager event for when a queued withdrawal is completed |
| `eth.eigenlayer.strategy_manager_withdrawal_delay_blocks_set`    | StrategyManager event for when the `withdrawalDelayBlocks` variable is modified from `previousValue` to `newValue` |
| `eth.eigenlayer.strategy_manager_withdrawal_queued`              | StrategyManager event for when a new withdrawal is queued by `depositor` |
| `eth.eigenlayer.withdrawal_recipient_balances`                   | Current per-block, Ether balance for each recipient of an eigenpod withdrawal |
| `eth.eigenlayer.withdrawal_router_balances`                      | Currentper-block, Ether balance for the DelayedWithdrawalRouter contract |
| `eth.eigenlayer.withdrawal_router_claimed`                       | Decoded `DelayedWithdrawalClaimed` events for the `DelayedWithdrawalRouter` contract |
| `eth.eigenlayer.withdrawal_router_created`    | Decoded `DelayedWithdrawalCreated` events from the `DelayedWithdrawalRouter` contract |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN eth.eigenlayer
```
