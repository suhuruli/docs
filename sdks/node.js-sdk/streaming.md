# Streaming

The `@spiceai/spice` SDK supports streaming partial results as they become available.

This can be used to enable more efficient pipelining scenarios where processing each row of the result set can happen independently.

The function signature of `Client.query` takes an optional `onData` callback that will be passed partial results as they become available.

```javascript
public async query(
    queryText: string,
    onData: ((data: Table) => void) | undefined = undefined
  ): Promise<Table>
```

Let's see how this works in practice. Imagine we want to iterate over all of the owners of the Bored Ape Yacht Club NFT collection. There are 10000 NFTs in the collection, so we could write the below query that would return all 10k NFTs with their owners in one call:

```javascript
import { SpiceClient } from "@spiceai/spice";

const spiceClient = new SpiceClient(process.env.API_KEY);
const query = `
SELECT token_id, owner 
FROM eth.nft_owners 
WHERE token_address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d'
ORDER BY CAST(token_id AS NUMERIC)
`
const allBaycOwners = await spiceClient.query(query)
allBaycOwners.toArray().forEach((row) => {
    processNFTOwner(row.toJSON())
});
```

The result is that we call the `processNFTOwner` function 10k times, but we have to wait for all of the data to arrive before we can even begin the processing.

We can do better by processing the NFT owners as the results are streamed to the SDK. To take advantage of this, simply move the logic to process the data in the `onData` callback instead of the result of the `query` API. Rewriting the above code in this format looks like:

```javascript
import { SpiceClient } from "@spiceai/spice";

const spiceClient = new SpiceClient(process.env.API_KEY);
const query = `
SELECT token_id, owner 
FROM eth.nft_owners 
WHERE token_address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d'
ORDER BY CAST(token_id AS NUMERIC)
`
await spiceClient.query(query, (partialData) => {
    partialData.toArray().forEach((row) => {
        processNFTOwner(row.toJSON())
    });
})
```

This will yield the same result as before: `processNFTOwner` will be called 10k times, but it can start processing the data earlier.

To demonstrate the effect of streaming the data, the following snippet keeps track of all the seen data and writes out how much of dataset it has processed.

```javascript
import { SpiceClient } from "@spiceai/spice"

const API_KEY = process.env['API_KEY']

// Retrieve all Bored Ape Yacht Club owners in order by token_id
const query = `
SELECT token_id, owner 
FROM eth.nft_owners 
WHERE token_address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d'
ORDER BY CAST(token_id AS NUMERIC)
`;

let baycOwners = {};
const processNFTOwner = (row) => {
  // Some processing of the NFT Owner.
  baycOwners[row.token_id] = row.owner;
};

const spiceClient = new SpiceClient(API_KEY);
await spiceClient.query(query, (data) => {
  data.toArray().forEach((row) => {
    processNFTOwner(row.toJSON());
  });

  console.log("Current size", Object.keys(baycOwners).length);
});

```

Run this snippet yourself to see how it works using Replit. (Click the Fork Repl button)

[https://replit.com/@phillipleblanc/Spice-NodeJS-Streaming-Example#index.js](https://replit.com/@phillipleblanc/Spice-NodeJS-Streaming-Example#index.js)
