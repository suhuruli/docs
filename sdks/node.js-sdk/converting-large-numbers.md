# Converting Large Numbers

Large numbers are returned from the Node.js SDK as an `Uint32Array`. This is because Javascript cannot represent [integers larger than 53 bits](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number), whereas our platform can return integers up to 128 bits.&#x20;

Since Javascript cannot natively represent integers larger than 53 bits, the [Arrow JS library](https://arrow.apache.org/docs/js/index.html) splits it into an array of 32-bit integers. It is possible to convert these values to a string or [BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/BigInt) through the use of a utility function in the Arrow library.

```javascript
const client = require('@spiceai/spice');
const arrow = require('apache-arrow');

const spiceClient = new client.SpiceClient('API-KEY')
const table = await spiceClient.query(`
  SELECT "value" 
  FROM eth.transactions 
  WHERE hash = '0xceb2a83e69c919f88b1c8b6e643d5f8d3cf7d44f0d53147c8a2f74ce1f1d4532'`)
const tableArray = table.toArray()
console.log(tableArray[0].value)
// DecimalBigNum(4) [Uint32Array] [ 1046478848, 2011190977, 342674185, 0 ]
console.log(arrow.util.bignumToString(tableArray[0].value))
// 6321223000000000000000000000
console.log(arrow.util.bignumToBigInt(tableArray[0].value))
// 6321223000000000000000000000
```
