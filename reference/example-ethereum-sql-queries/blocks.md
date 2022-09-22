# Blocks

### Get Latest Block Number

Gets the number of the latest block in the chain.

**Typical query time**: < 1 second.

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT max(number) AS latest_block_number
FROM eth.recent_blocks
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT max(number) AS latest_block_number
FROM polygon.recent_blocks
```
{% endtab %}
{% endtabs %}

### Last 5000 Blocks

Gets basic information for the last 5000 blocks in the chain.

{% hint style="info" %}
To get access to more than 500 results, use the [Apache Arrow Flight API](broken-reference/).
{% endhint %}

**Typical query time**: 2 seconds

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT number, "timestamp", hash, transaction_count, gas_used
FROM eth.blocks
ORDER BY number DESC
LIMIT 5000
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT number, "timestamp", hash, transaction_count, gas_used
FROM polygon.blocks
ORDER BY number DESC
LIMIT 5000
```
{% endtab %}
{% endtabs %}

### Most Ethereum Burned in a Block

Returns a list of the blocks with the highest amount of Ethereum burned, sorted in descending order.

**Typical query time**: 2 seconds

{% hint style="info" %}
This query only works for Ethereum
{% endhint %}

```sql
SELECT number,
       sum(gas_used * (base_fee_per_gas / 1e18)) AS eth_burned
FROM eth.blocks
WHERE base_fee_per_gas IS NOT NULL
GROUP BY eth.blocks.number
ORDER BY eth_burned DESC
LIMIT 500
```

### Get a Random Block

Gets basic information about a random block in the chain.

**Typical query time**: <3 seconds

{% tabs %}
{% tab title="Ethereum" %}
```sql
WITH random_block AS (
    SELECT mod(cast(floor(random() * 1e9) AS numeric), latest_block.number) AS number
        FROM (
            SELECT max(number) AS number FROM eth.blocks
        ) AS latest_block
)
SELECT number, "timestamp", hash, transaction_count, gas_used 
FROM eth.blocks
WHERE number = (SELECT number FROM random_block)
```
{% endtab %}

{% tab title="Polygon" %}
```sql
WITH random_block AS (
    SELECT mod(cast(floor(random() * 1e9) AS numeric), latest_block.number) AS number
        FROM (
            SELECT max(number) AS number FROM polygon.blocks
        ) AS latest_block
)
SELECT number, "timestamp", hash, transaction_count, gas_used 
FROM polygon.blocks
WHERE number = (SELECT number FROM random_block)
```
{% endtab %}
{% endtabs %}

### Blocks with the Highest Number of Transactions

Gets the list of blocks with the highest number of transactions that were included in that block, sorted in descending order.

**Typical query time**: 1 second

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT number, "timestamp", transaction_count, gas_used
FROM eth.blocks 
ORDER BY transaction_count DESC 
LIMIT 500
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT number, "timestamp", transaction_count, gas_used
FROM polygon.blocks 
ORDER BY transaction_count DESC 
LIMIT 500
```
{% endtab %}
{% endtabs %}
