# Logs

### Find arbitrary smart contract events

Use Spice to find any smart contract event by filtering on the first value of the `topics` column.&#x20;

As an example, to get all on-chain OpenSea NFT sales, use the `OrderFulfilled` event hash: `0x9d9af8e38d66c62e2c12f0225249fd9d721c54b83f48d9352c97c6cacdcb6f31`

{% tabs %}
{% tab title="Ethereum" %}
```sql
SELECT * 
FROM eth.recent_logs 
WHERE address = '0x00000000006c3852cbef3e08e8df289169ede581' -- OpenSea Seaport Contract
 AND  topics[0] = '0x9d9af8e38d66c62e2c12f0225249fd9d721c54b83f48d9352c97c6cacdcb6f31'
-- OrderFulfilled(bytes32,address,address,address,(uint8,address,uint256,uint256)[],(uint8,address,uint256,uint256,address)[])
```
{% endtab %}

{% tab title="Polygon" %}
```sql
SELECT * 
FROM polygon.recent_logs 
WHERE address = '0x00000000006c3852cbef3e08e8df289169ede581' -- OpenSea Seaport Contract
 AND  topics[0] = '0x9d9af8e38d66c62e2c12f0225249fd9d721c54b83f48d9352c97c6cacdcb6f31'
-- OrderFulfilled(bytes32,address,address,address,(uint8,address,uint256,uint256)[],(uint8,address,uint256,uint256,address)[])
```
{% endtab %}
{% endtabs %}
