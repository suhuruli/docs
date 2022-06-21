# Streaming

The `spicepy` SDK supports streaming partial results as they become available.

This can be used to enable more efficient pipelining scenarios where processing each row of the result set can happen independently.

&#x20;`spicepy` enables streaming through the use of the [pyarrow Flight API](https://arrow.apache.org/docs/dev/python/api/flight.html).

The object returned from `spicepy.Client.query()` is a [`pyarrow.flight.FlightStreamReader`](https://arrow.apache.org/docs/dev/python/generated/pyarrow.flight.FlightStreamReader.html#pyarrow.flight.FlightStreamReader).

```python
>>> from spicepy import Client
>>> import os
>>> client = Client(os.environ["API_KEY"])
>>> rdr = client.query("SELECT * FROM eth.recent_blocks")
<pyarrow._flight.FlightStreamReader object at 0x1059c9980>
```

Calling `to_pandas()` on the `FlightStreamReader` will wait for the stream to return all of the data before returning a pandas DataFrame.

To operate on partial results while the data is streaming, we will take advantage of the [`read_chunk()`](https://arrow.apache.org/docs/dev/python/generated/pyarrow.flight.FlightStreamReader.html#pyarrow.flight.FlightStreamReader.read\_chunk) method on `FlightStreamReader`. This returns a `FlightStreamChunk`, which has a `data` attribute that is a [`RecordBatch`](https://arrow.apache.org/docs/dev/python/generated/pyarrow.RecordBatch.html#pyarrow.RecordBatch). Once we have the RecordBatch, we can call `to_pandas()` on it to return the partial data as a pandas DataFrame. When the stream has ended, calling `read_chunk()` will raise a `StopIteration` exception that we can catch.

Let's see how this works in practice. Imagine we want to iterate over all of the owners of the Bored Ape Yacht Club NFT collection. There are 10000 NFTs in the collection, so we could write the below query that would return all 10k NFTs with their owners in one call:

```python
from spicepy import Client

client = Client(os.environ["API_KEY"])
query = """
    SELECT token_id, owner 
    FROM eth.nft_owners 
    WHERE token_address = '0xbc4ca0eda7647a8ab7c2061c2e118a18a936f13d'
    ORDER BY CAST(token_id AS NUMERIC)
"""

reader = client.query(query)
baycOwners = reader.read_pandas()
```

The result is that we get a pandas DataFrame with all 10k NFTs, but we have to wait for all of the data to arrive before we can begin processing.

We can do better by processing the NFT owners as the results are streamed down. To take advantage of this, we need to call the `read_chunk()` method on the returned `FlightStreamReader` object to process each chunk of data as it arrives. Rewriting the above code in this format looks like:

```python
reader = client.query(query)

has_more = True
while has_more:
    try:
        flight_batch = reader.read_chunk()
        record_batch = flight_batch.data
        processChunk(record_batch.to_pandas())
    except StopIteration:
        has_more = False
```
