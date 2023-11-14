---
description: Ethereum Native Wallet Balance tables available to query via SQL
---

# Wallet Balances

**Native Wallet Balance specific tables**

| Table Name                                       | Description                                                      |
| ------------------------------------------------ | ---------------------------------------------------------------- |
| [`eth.wallet_balances`](eth.wallet\_balances.md) | A block-level view of all changes to any account's Ether balance |
| `eth.recent_wallet_balances`                     | Balances changed in the last 30 minutes, \~128 blocks            |

The columns and their schema for each table can be viewed with the describe \<table> command. For example:

```sql
-- Show the columns available
DESCRIBE eth.wallet_balances;
```

One of the most fundamental queries to make on any blockchain is the native currency balance of a wallet. The `eth.wallet_balances` table contains a block-level view of all Ether balance changes due to gas fees, withdrawals, and committed external and internal (contract) transactions.

Getting the balance of a wallet becomes a simple act of querying the absolute balance (in gwei) at the last block that it changed:

```sql
WITH ranked_balances AS (
    SELECT address, balance_gwei, balance_usd, ROW_NUMBER() OVER (PARTITION BY address ORDER BY block_number DESC) AS rn
    FROM eth.wallet_balances
)

SELECT address, balance_gwei, balance_usd
FROM ranked_balances WHERE rn = 1 and address = LOWER('0x28c6c06298d514db089934071355e5743bf21d60')
```

This dataset contains the `balance_gwei` (Ether balance, in gwei) at the block in question, as well as an estimated `balance_usd` in USD. In cases where the gwei balance is too large to represent efficiently, the full value can be extracted programmatically from the hexadecimal string representation in the `balance_hex` column.

Historical wallet balance data can also be queried:

```sql
-- get the net peak-to-peak balance change for a wallet over the last week
SELECT address, max(balance_gwei) - min(balance_gwei) as "last week delta (gwei)", max(balance_usd) - min(balance_usd) as "last week delta (USD)"
FROM eth.wallet_balances
WHERE address = '0x28c6c06298d514db089934071355e5743bf21d60'
AND block_timestamp > UNIX_TIMESTAMP() - 7*24*60*60*1000
GROUP BY address
```

Additionally, the most recent 30 minutes of wallet balance changes are cached in a high performance recent table `eth.recent_wallet_balances`.

The above datasets combine to facilitate rich, performant, historical data access beyond the standard offerings in class. Going forward, additional SQL representations that would make other common access patterns even easier are being consider. Reach out on Discord if you have use cases not covered here.

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

<table><thead><tr><th width="398">Table Name</th><th>Indexed Columns</th></tr></thead><tbody><tr><td><code>eth.wallet_balances</code></td><td><code>block_number</code> <code>block_timestamp</code> <code>address</code></td></tr><tr><td><code>eth.recent_wallet_balances</code></td><td><code>block_number</code> <code>block_timestamp</code> <code>address</code></td></tr></tbody></table>
