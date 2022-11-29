# BTC

#### BTC exchange specific tables

| Table Name              | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| `prices.btc.coinbase`   | HLOC values for BTC at 1 minute granularity from Coinbase |
| `prices.btc.gemini`     | HLOC values for BTC at 1 minute granularity from Gemini   |
| `prices.btc.uniswap_v2` | HLOC values for BTC at 1 minute granularity from Uniswap  |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE prices.btc.coinbase;
DESCRIBE prices.btc.gemini;
DESCRIBE prices.btc.uniswap_v2;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name              | Indexed Columns |
| ----------------------- | --------------- |
| `prices.btc.coinbase`   | `timestamp`     |
| `prices.btc.gemini`     | `timestamp`     |
| `prices.btc.uniswap_v2` | `timestamp`     |
