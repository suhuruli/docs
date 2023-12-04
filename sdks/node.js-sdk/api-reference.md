# API Reference

## SpiceClient(apiKey, url)

The top-level object that connects to Spice.ai

* `apiKey`(string, required): API key to authenticate with the endpoint
* `url`(string, optional): URL of the endpoint to use (default: flight.spiceai.io:443)

```javascript
import { SpiceClient } from "@spiceai/spice";

const spiceClient = new SpiceClient('API_KEY');
```

### SpiceClient Methods

**query**(queryText: string, onData: (partialData: [Table](https://arrow.apache.org/docs/js/classes/Arrow\_dom.Table.html)) => void) => [Table](https://arrow.apache.org/docs/js/classes/Arrow\_dom.Table.html)

* `queryText`: (string, required): The SQL query to execute
* `onData`: (callback, optional): The callback function that is used for handling [streaming](streaming.md) data.

`query` returns an Apache Arrow [Table](https://arrow.apache.org/docs/js/classes/Arrow\_dom.Table.html).

To get the data in JSON format, iterate over each row by calling [`toArray()`](https://arrow.apache.org/docs/js/classes/Arrow\_dom.Table.html#toArray) on the table and call [`toJSON()`](https://arrow.apache.org/docs/js/classes/Arrow\_dom.StructRow.html#toJSON) on each row.

```javascript
const table = await spiceClient.query("SELECT * from eth.recent_blocks LIMIT 10")
table.toArray().forEach((row) => {
  console.log(row.toJSON());
});
```

Get all of the elements for a column by calling [`getChild(name: string)`](https://arrow.apache.org/docs/js/classes/Arrow\_dom.Table.html#getChild) and then calling `toJSON()` on the result.

```javascript
const table = await client.query(
  'SELECT number, base_fee_per_gas / 1e9 AS base_fee_per_gas_gwei FROM eth.recent_blocks limit 3'
);

let baseFeeGwei = tableResult.getChild("base_fee_per_gas_gwei");
console.log(baseFeeGwei?.toJSON())
```

**getLatestPrices**(pairs: string[]) => LatestPrices
* `pairs`: (Array of string, required): The crypto/currency pairs, for example ["BTC-USD", "USD-ETH"]. 

`getLatestPrices` returns the latest prices for a list of asset pairs. `getLatestPrices` returns
```javascript
LatestPrice {
  [pair: string]: {
    prices?: { [exchange: string]: string };
    minPrice?: string;
    maxPrice?: string;
    avePrice?: string;
  }
}
```

Example API query
```javascript
  let pairs = ["BTC-USD", "USD-ETH"]; 
  const price = await client.getLatestPrices([pairs]);
  pairs.forEach((v: string) => {
    price[v].prices.forEach((exchange: string) => {
      console.log("pair=" + v, "exchange=" + exchange, price[v].prices[exchange])
    })
  })
```

**getPrices**(pair: string[], startTime?: number, endTime?: number, granularity?: string) => HistoricalPrices
* `pairs`: (Array of string, required): The crypto/currency pairs, for example ["BTC-USD", "USD-ETH"]. 
* `startTime`: start time milliseconds since Unix Epoch
* `endTime`: end time milliseconds since Unix Epoch
* `granularity`: valid [duration](https://docs.spice.ai/core-concepts/duration-literals)

`getPrices` returns prices for a list of asset pairs for a given period of time. `getPrices` returns 
```javascript
HistoricalPrices {
  [pair: string]: {
    timestamp: string;
    price: number;
    high?: number;
    low?: number;
    open?: number;
    close?: number;
  }
}
```

Example API Query
```javascript
const prices = await client.getPrices(
  pairs,
  new Date('2023-01-01').getTime() / 1000,
  new Date('2023-01-02').getTime() / 1000,
  '1h'
);

pairs.forEach((v: string) => {
  console.log(price[v])
})
```
