# Transaction Inputs/Outputs

### Get Addresses with Most BTC Sent

Gets the top 10 addresses that had the most bitcoin sent to them in the last 30 minutes.

**Typical query time**: 1 second

```sql
SELECT "value" / 1e8 AS btc_transferred, addresses, script_asm, type, block_number
FROM btc.recent_transaction_outputs ORDER BY "value" DESC
LIMIT 10
```

### Get Addresses that "Spent" the Most Bitcoin

Gets the top 10 addresses that "spent" the most bitcoin in the last 30 minutes (i.e. the amount of bitcoin that wasn't transferred back to the original address in the transaction)

**Typical query time**: 2 seconds

```sql
WITH flattened_addresses_outputs AS (
    SELECT *, flatten(addresses) as flattened_address FROM btc.recent_transaction_outputs
), flattened_addresses_inputs AS (
    SELECT *, flatten(addresses) as flattened_address FROM btc.recent_transaction_inputs
)
SELECT (MAX(outputs."value") - MAX(inputs."value")) / 1e8 as btc_spent, MAX(outputs."value") / 1e8 as output_value_btc, MAX(inputs."value") / 1e8 as input_value_btc, outputs.transaction_hash, outputs.flattened_address as address
FROM flattened_addresses_outputs outputs
    INNER JOIN flattened_addresses_inputs inputs
    ON outputs.flattened_address = inputs.flattened_address AND outputs.transaction_hash = inputs.transaction_hash
GROUP BY outputs.transaction_hash, outputs.flattened_address
ORDER BY MAX(outputs."value") - MAX(inputs."value") DESC
LIMIT 10
```
