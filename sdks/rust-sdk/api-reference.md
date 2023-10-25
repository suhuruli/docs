# API Reference

## SpiceClient

The top-level object that connects to Spice.ai

`Query` can be accessed from SpiceClient, `Prices functions` can be accessed from SpiceClient.prices

```rust
pub struct SpiceClient {
    flight: SqlFlightClient,
    pub prices: PricesClient,
}
```

### SpiceClient Methods

**new**(api\_key: \&str) -> Self

* `api_key`(\&str, required): API key to authenticate with the endpoint

**query**(\&mut self, query: \&str) -> Result\<FlightRecordBatchStream, Box\<dyn Error>>

```rust
use spice_rs::Client;

let client = Client::new(api_key).await;
```

* `query`: (\&str, required): The SQL query to execute

`query` returns an Apache Arrow [FlightRecordBatchStream](https://arrow.apache.org/rust/arrow\_flight/decode/struct.FlightRecordBatchStream.html)

```rust
let flight_data_stream = client.query("SELECT * FROM eth.recent_blocks LIMIT 10;").await.expect("Error executing query");
```

To get the data in Arrow Array [RecordBatch](https://arrow.apache.org/rust/arrow\_array/record\_batch/struct.RecordBatch.html), iterate over [FlightRecordBatchStream](https://arrow.apache.org/rust/arrow\_flight/decode/struct.FlightRecordBatchStream.html)

```rust
while let Some(batch) = flight_data_stream.next().await {
                    match batch {
                        Ok(batch) => {
                            /* process batch */
                            println!("{:?}", batch)
                        },
                        Err(e) => {
                            /* handle error */
                        },
                    };
```

**.prices.get\_supported\_pairs**(\&self) -> Result\<Vec, Box\<dyn Error>>

`get_supported_pairs` returns supported pairs by prices client

example api query

```rust
let result = spice_client
    .prices
    .get_supported_pairs()
    .await
    .expect("Error getting supported pairs");
println!("{:?}", result);
```

**.prices.get\_prices**(\&self, pairs: &\[\&str]) -> Result\<LatestPricesResponse, Box\<dyn Error>>

* `pairs`: (&\[\&str], required): The crypto/currency pairs, for example &\["BTC-USD", "ETH-USD"]

`get_prices` returns a `LatestPricesResponse` struct

```rust
pub struct LatestPricesResponse {
    // This assumes each key in the JSON (like "BTC-USDC", "LTC-USDT") is dynamic and represents a currency pair
    #[serde(flatten)]
    pub prices: HashMap<String, LatestPriceDetail>,
}
```

`LatestPricesResponse` consists of `LatestPricesResponse` struct

```rust
pub struct LatestPriceDetail {
    #[serde(deserialize_with = "string_to_float_map")]
    pub prices: HashMap<String, f64>,
    #[serde(
        rename = "minPrice",
        default,
        deserialize_with = "string_to_float_option"
    )]
    pub min_price: Option<f64>,
    #[serde(
        rename = "maxPrice",
        default,
        deserialize_with = "string_to_float_option"
    )]
    pub max_price: Option<f64>,
    #[serde(
        rename = "meanPrice",
        default,
        deserialize_with = "string_to_float_option"
    )]
    pub mean_price: Option<f64>,
}
```

example api query

```rust
let result = client
    .prices
    .get_prices(&["BTC-USD", "ETH-USD"])
    .await
    .expect("Error getting prices");
println!("{:?}", result);
```

**.prices.get\_historical\_prices**( \&self, pairs: &\[\&str], start: Option\<DateTime>, end: Option\<DateTime>, granularity: Option<\&str>, ) -> Result\<HashMap\<String, Vec\<HistoricalPriceData>>, Box\<dyn Error>>

* `pairs`: (&\[\&str], required): The crypto/currency pairs, for example &\["BTC-USD", "ETH-USD"]
* `start`: start time milliseconds since Unix Epoch
* `end`: end time milliseconds since Unix Epoch
* `granularity`: valid [duration](https://docs.spice.ai/core-concepts/duration-literals)

`get_historical_prices` returns a vector of `HistoricalPrices` struct

```rust
pub struct HistoricalPriceData {
    pub timestamp: DateTime<Utc>,
    pub price: f64,
    pub high: Option<f64>,
    pub low: Option<f64>,
    pub open: Option<f64>,
    pub close: Option<f64>,
}
```

example api query

```rust
let start_time = Utc.timestamp_opt(1697669766, 0).single();
let end_time = Utc.timestamp_opt(1697756166, 0).single();
let result = spice_client
    .prices
    .get_historical_prices(&["BTC-USD", "ETH-USD"], start_time, end_time, Some("1h"))
    .await
    .expect("Error getting historical prices");
println!("{:?}", result);
```
