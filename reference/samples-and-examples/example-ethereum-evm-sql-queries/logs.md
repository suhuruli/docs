# Logs

### Recent NFT sales from Opensea

**Typical query time**: <1 seconds

```sql
SELECT *
FROM eth.recent_logs 
WHERE (
    address='0x00000000006c3852cbef3e08e8df289169ede581' OR -- OpenSea Seaport Contract 1.1
    address='0x00000000000006c7676171937c444f6bde3d6282' OR -- OpenSea Seaport Contract 1.2
    address='0x0000000000000ad24e80fd803c6ac37206a45f15' OR -- OpenSea Seaport Contract 1.3
    address='0x00000000000001ad428e4906ae43d8f9852d0dd6' OR -- OpenSea Seaport Contract 1.4
    address='0x00000000000000adc04c56bf30ac9d3c0aaf14dc') -- OpenSea Seaport Contract 1.5
AND  topics[0] = '0x9d9af8e38d66c62e2c12f0225249fd9d721c54b83f48d9352c97c6cacdcb6f31'
```
