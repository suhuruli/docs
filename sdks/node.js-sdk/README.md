# 🆕 Node.js SDK

The Node.js SDK [spice.js](https://www.npmjs.com/package/@spiceai/spice) is the easiest way to use and query Spice with Node.js.

### Requirements

* [Node.js 16+](https://nodejs.org/)

### Installation

`npm install @spiceai/spice --save`

or

`yarn add @spiceai/spice`

### Usage

Import `SpiceClient` and instantiate a new instance with an API Key.

You can then submit queries using the `query` function.

```javascript
import { SpiceClient } from "@spiceai/spice";

const spiceClient = new SpiceClient("API_KEY");
const table = await spiceClient.query(
  'SELECT number, "timestamp", gas_used FROM eth.recent_blocks LIMIT 10'
);
console.table(table.toArray());
```

`SpiceClient` has the following arguments:

* `apiKey` (string, required): API key to authenticate with the endpoint.
* `url` (string, optional): URL of the endpoint to use (default: flight.spiceai.io:443)

### Contributing

Contribute to or file an issue with the Spice.js library at [https://github.com/spiceai/spice.js](https://github.com/spiceai/spice.js)
