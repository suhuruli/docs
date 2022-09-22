# Transactions

### All Transactions From/To an Address

Gets all of the transactions that involve a single address.

**Typical query time**: \~15 seconds

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT hash, block_number, nonce, from_address, to_address, "value", gas  
FROM eth.transactions 
WHERE from_address = LOWER('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045')
UNION ALL
SELECT hash, block_number, nonce, from_address, to_address, "value", gas  
FROM eth.transactions 
WHERE to_address = LOWER('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045')
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT hash, block_number, nonce, from_address, to_address, "value", gas  
FROM polygon.transactions 
WHERE from_address = LOWER('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045')
UNION ALL
SELECT hash, block_number, nonce, from_address, to_address, "value", gas  
FROM polygon.transactions 
WHERE to_address = LOWER('0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045')
```
{% endtab %}
{% endtabs %}

### Largest Ethereum Transfer in January 2021

Gets the transaction that involved the largest transfer of Ethereum in January 2021.

**Typical query time**: \~20 seconds

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT "value" / 1e18 as max_eth_transferred, block_number, hash, TO_TIMESTAMP(block_timestamp) as block_timestamp
FROM eth.transactions 
WHERE block_timestamp >= UNIX_TIMESTAMP('2021-01-01 00:00:00')
   AND block_timestamp <= UNIX_TIMESTAMP('2021-01-31 23:59:59')
ORDER BY max_eth_transferred DESC
LIMIT 1
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT "value" / 1e18 as max_matic_transferred, block_number, hash, TO_TIMESTAMP(block_timestamp) as block_timestamp
FROM polygon.transactions 
WHERE block_timestamp >= UNIX_TIMESTAMP('2021-01-01 00:00:00')
   AND block_timestamp <= UNIX_TIMESTAMP('2021-01-31 23:59:59')
ORDER BY max_matic_transferred DESC
LIMIT 1
```
{% endtab %}
{% endtabs %}
