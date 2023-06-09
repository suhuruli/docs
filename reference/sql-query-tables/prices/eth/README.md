# ETH

#### ETH exchange specific tables

| Table Name                                           | Description                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| [`prices.eth.coinbase`](prices.eth.coinbase.md)      | HLOC values for ETH at 1 minute granularity from Coinbase  |
| [`prices.eth.gemini`](prices.eth.gemini.md)          | HLOC values for ETH at 1 minute granularity from Gemini    |
| [`prices.eth.sushiswap`](prices.eth.sushiswap.md)    | HLOC values for ETH at 1 minute granularity from Sushiswap |
| [`prices.eth.uniswap_v2`](prices.eth.uniswap\_v2.md) | HLOC values for ETH at 1 minute granularity from Uniswap   |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE prices.eth.coinbase;
DESCRIBE prices.eth.gemini;
DESCRIBE prices.eth.sushiswap;
DESCRIBE prices.eth.uniswap_v2;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name              | Indexed Columns |
| ----------------------- | --------------- |
| `prices.eth.coinbase`   | `timestamp`     |
| `prices.eth.gemini`     | `timestamp`     |
| `prices.eth.sushiswap`  | `timestamp`     |
| `prices.eth.uniswap_v2` | `timestamp`     |
