---
description: Tables containing historical prices of tokens
---

# Prices

Each historical prices dataset is structured with a top level table that contains aggregated prices across all supported exchanges. Each supported exchange then has its own subtable where prices from just that exchange are available.&#x20;

Prices are available in High-Low-Open-Close (HLOC) format.

#### Top level token historical token prices tables

| Table Name   | Description                                                                 |
| ------------ | --------------------------------------------------------------------------- |
| `prices.eth` | HLOC values for ETH at 1 minute granularity aggregated across all exchanges |
| `prices.btc` | HLOC values for BTC at 1 minute granularity aggregated across all exchanges |
| `prices.ltc` | HLOC values for LTC at 1 minute granularity aggregated across all exchanges |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN prices
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE prices.eth;
DESCRIBE prices.btc;
DESCRIBE prices.ltc;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name   | Indexed Columns |
| ------------ | --------------- |
| `prices.eth` | `timestamp`     |
| `prices.btc` | `timestamp`     |
| `prices.ltc` | `timestamp`     |
