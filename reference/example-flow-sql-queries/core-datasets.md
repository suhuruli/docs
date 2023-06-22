# Core Datasets

### Get Latest Block Height

Gets the height of the latest block in the chain.

```sql
SELECT max(height) AS latest_block_height
FROM flow.recent_blocks
```

### Wallets that sent the most recent transactions

Finds the top 10 wallets that sent the most transactions in the last 30 minutes

```sql
SELECT count(1) AS num_tx_sent, proposal_key_address
FROM flow.recent_transactions
GROUP BY proposal_key_address
ORDER BY num_tx_sent DESC
LIMIT 10
```

### Recent transactions where the proposer didn't pay

Finds examples of transactions where the proposer of the transaction wasn't the address that paid for it's execution.

```sql
SELECT * FROM flow.recent_transactions 
WHERE proposal_key_address != payer
LIMIT 10
```

### Number of transactions per block

```sql
SELECT count(1) AS num_tx, block_height
FROM flow.recent_transactions
GROUP BY block_height
LIMIT 10
```

### Events that represent NFT Withdrawals/Deposits

The raw event data that corresponds to an NFT Withdrawal or Deposit.

```sql
SELECT *
FROM flow.recent_events
WHERE type LIKE '%.Withdraw' OR type LIKE '%.Deposit'
LIMIT 10
```

### Events from a specific contract

Find all recent event that came from a specific contract

```sql
SELECT *
FROM flow.recent_events
WHERE type LIKE 'A.0b2a3299cc857e29.TopShot.%'
LIMIT 10
```

### Get Event Payload

Get the UTF8-encoded view of the raw JSON event payload.

```sql
SELECT CONVERT_FROM(payload, 'UTF8') AS payload_utf8
FROM flow.recent_events
LIMIT 10
```
