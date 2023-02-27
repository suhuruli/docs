# Wallet Balances

#### **Wallet Balance tables**

| Table Name                   | Description                                                      |
| ---------------------------- | ---------------------------------------------------------------- |
| `eth.wallet_balance_updates` | A view of all block-level changes to any account's Ether balance |
| `eth.daily_wallet_balances`  | A daily aggregation of all block-level deltas                    |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```sql
/* Show the columns available */
DESCRIBE eth.wallet_balance_updates;
```

One of the most fundamental queries to make on any blockchain is the native currency balance of a wallet. The `eth.wallet_balance_updates` table contains a block-level aggregation of all Ether balance changes due to gas fees and committed transactions.

Getting the balance of a wallet becomes a simple act of summing all relevant updates:

```sql
SELECT address, sum(balance_wei) as "absolute balance (wei)" FROM eth.wallet_balance_updates WHERE address = '0x123deadbeef'
```

This dataset includes all historical data too:

```sql
-- get the net balance change for a wallet in the last hour
SELECT address, sum(balance_wei) as "last hour delta (wei)" FROM eth.wallet_balance_updates WHERE address = '0x123deadbeef' AND block_timestamp > NOW() - 60*60*1000
```

While most accounts only ever make a handful of transactions in their lifetime, other wallets are extremely busy. Aggregating balances on-demand would not meet performance targets for these wallets. To address this, we also provide historical absolute-value daily snapshot balances in `eth.daily_wallet_balances`.

To employ this optimization, first query for the latest daily snapshot before your target block:

```sql
SELECT block_number, balance_wei as "delta" FROM eth.daily_wallet_balances WHERE address = '0x789exchange' AND block_timestamp <= NOW()
```

Then query for the incremental balance change since that time using the earlier technique:

```sql
SELECT sum(balance_wei) as "daily" FROM eth.wallet_balance_updates WHERE address = '0x789exchange' AND block_number > _block_number_from previous query_
```

The wallet balance at your target timestamp is the sum of these two balances (`daily + delta`).

**Note**: recent daily balance snapshots may not always exist for a particular wallet, for example, if the wallet is new or today's balance was calculated on a reverted block (due to fork misprediction). Further, daily balances are scheduled to optimize for overall query performance; they are not guaranteed to be processed at any specific time. There may even be _multiple_ "daily" balances recorded for a wallet throughout a single day!

The above datasets combine to facilitate rich, performant, historical data access beyond the standard offerings in class. Going forward, we are considering additional SQL representations that would make other common access patterns even easier. Reach out on Discord if you have use cases not covered here.

