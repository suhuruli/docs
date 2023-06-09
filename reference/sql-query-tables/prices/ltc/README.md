# LTC

#### LTC exchange specific tables

| Table Name                                      | Description                                               |
| ----------------------------------------------- | --------------------------------------------------------- |
| [`prices.ltc.coinbase`](prices.ltc.coinbase.md) | HLOC values for LTC at 1 minute granularity from Coinbase |
| [`prices.ltc.gemini`](prices.ltc.gemini.md)     | HLOC values for LTC at 1 minute granularity from Gemini   |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE prices.ltc.coinbase;
DESCRIBE prices.ltc.gemini;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name            | Indexed Columns |
| --------------------- | --------------- |
| `prices.ltc.coinbase` | `timestamp`     |
| `prices.ltc.gemini`   | `timestamp`     |
