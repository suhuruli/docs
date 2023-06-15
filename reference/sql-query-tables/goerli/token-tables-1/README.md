---
description: Goerli Wallet Balance tables available to query via SQL
---

# Wallet Balance Tables

**Links**

* [Ethereum Wallet Balances](../../ethereum/wallet-balances/)

#### Wallet Balances specific tables

<table><thead><tr><th width="374">Table Name</th><th>Description</th></tr></thead><tbody><tr><td><a href="goerli.wallet_balances.md"><code>goerli.wallet_balances</code></a></td><td>A block-level view of all changes to any account's Ether balance</td></tr><tr><td><code>goerli.recent_wallet_balances</code></td><td>Balances changed in the last 30 minutes, ~128 blocks</td></tr></tbody></table>

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE goerli.wallet_balances;
DESCRIBE goerli.recent_wallet_balances;
```

#### Improving query performance - indexed columns

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

<table><thead><tr><th width="398">Table Name</th><th>Indexed Columns</th></tr></thead><tbody><tr><td><code>goerli.wallet_balances</code></td><td><code>block_number</code> <code>block_timestamp</code> <code>address</code></td></tr><tr><td><code>goerli.recent_wallet_balances</code></td><td><code>block_number</code> <code>block_timestamp</code> <code>address</code></td></tr></tbody></table>

x
