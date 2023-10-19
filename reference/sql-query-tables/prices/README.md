---
description: Tables containing historical prices of tokens
---

# Prices

## Prices

#### Aggregate price base type tables available to query

| View Name          | Description                                     |
| ------------------ | ----------------------------------------------- |
| `prices.all_pairs` | Per-minute price data for supported token pairs |
| `prices.assets`    | Tokens supported on Spice AI with metadata      |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE prices.all_pairs;
DESCRIBE prices.assets;
-- etc.
```

#### Per-pair price base type tables available to query

Historical prices data is available in both pair specific tables named `prices.[Token0]_[Token2]` (e.g. prices.btc\_usdt) or in a single table containing all pairs named `prices.all_pairs`, which has an extra `pair` column to. For better performance, we recommend using the pair specific tables when you know the pairs that need to be queried at compile time and using the single table of all pairs when the pairs that need to be queried are determined dynamically at runtime.

Prices are available in High-Low-Open-Close (HLOC) format.

**Top level token historical token prices tables**

| Table Name                 | Description                                                      |
| -------------------------- | ---------------------------------------------------------------- |
| `prices.[Token0]_[Token2]` | HLOC values for pair `[Token0]-[Token2]` at 1 minute granularity |
| `prices.all_pairs`         | HLOC values for all pairs at 1 minute granularity                |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN prices
```

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE prices.btc_usdt;
DESCRIBE prices.all_pairs;
```

**Improving query performance - indexed columns**

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                 | Indexed Columns   |
| -------------------------- | ----------------- |
| `prices.[Token0]_[Token2]` | `timestamp`       |
| `prices.all_pairs`         | `timestamp, pair` |
