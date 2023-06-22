---
description: Flow base type tables available to query via SQL
---

# Core Tables

#### Flow base type tables available to query

| Table Name                                         | Description                                            |
| -------------------------------------------------- | ------------------------------------------------------ |
| [`flow.blocks`](flow.blocks.md)                    | Block headers                                          |
| [`flow.recent_blocks`](flow.blocks.md)             | Block headers from the last 30 minutes                 |
| [`flow.transactions`](flow.transactions.md)        | Block transactions                                     |
| [`flow.recent_transactions`](flow.transactions.md) | Block transactions from the last 30 minutes            |
| [`flow.events`](flow.events.md)                    | Events emitted by smart contracts during a transaction |
| [`flow.recent_events`](flow.events.md)             | Events from the last 30 minutes                        |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN flow
```
