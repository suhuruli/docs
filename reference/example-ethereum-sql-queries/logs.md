# Logs

### Find arbitrary smart contract events

Use Spice to find any smart contract event by filtering on the first value of the `topics` column.&#x20;

As an example, to get all on-chain OpenSea NFT sales, use the `OrdersMatched` event hash: `0xc4109843e0b7d514e4c093114b863f8e7d8d9a458c372cd51bfe526b588006c9`

```sql
SELECT * 
FROM eth.recent_logs 
WHERE address = '0x7f268357a8c2552623316e2562d90e642bb538e5' -- OpenSea Wyvern Contract
 AND  topics[0] = '0xc4109843e0b7d514e4c093114b863f8e7d8d9a458c372cd51bfe526b588006c9'
-- OrdersMatched(bytes32,bytes32,address,address,uint,uint,bytes32)
```
