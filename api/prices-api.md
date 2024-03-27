---
description: Asset (currency/token) Prices HTTP API documentation
---

# Asset Prices API

## Supported Pairs

The **`/v1/prices/pairs`** API returns a list of price pairs supported by the Spice.ai platform (non-exhaustive).

{% hint style="info" %}
The **/prices/pairs** endpoint only returns pairs provided directly from SpiceAI data. Price APIs aggregate data from other providers (decentralized exchanges e.g. Uniswap, centralized aggregators e.g. CoinMarketCap) and support significantly more pairs not listed by this endpoint.
{% endhint %}

## Get supported price pairs

<mark style="color:blue;">`GET`</mark> `https://data.spiceai.io/v1/prices/pairs`

Returns a list of token/currency Spice provided price pairs.

{% tabs %}
{% tab title="200: OK Pairs successfully returned" %}
```json
["BTC-USD", "ETH-USD", "LTC-USD"]
```
{% endtab %}
{% endtabs %}

## Latest Prices

The **`/v1/prices/{pair}`** API returns the spot (latest) prices of specified token/currency pairs from several exchanges (e.g. Binance, Coinbase, and Gemini), and aggregrates price measures (e.g. average, minimum).

## Get latest prices for symbol(s)

<mark style="color:blue;">`GET`</mark> `https://data.spiceai.io/v1/prices/{pair}`

For pair(s), returns the latest prices from several exchanges (e.g. Binance, Coinbase, and Gemini), and aggregate price measures (e.g. average, minimum).

#### Path Parameters

| Name | Type   | Description                                                                                                                                           |
| ---- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| pair | String | One currency/token pair symbols. Always upper-case. e.g. `BTC-ETH`, `ETH-SOL`. Multiple pairs can be provided by query parameters instead, see below. |

#### Query Parameters

| Name  | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                              |
| ----- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| pairs | String | One or more currency/token pairs symbols. Always upper-case. e.g. `BTC-ETH`, `ETH-SOL`. Multiple pairs can be provided in any of the following formats: `?pairs=BTC-ETH,ETH-SOL` or `?pairs=BTC-ETH&pairs=ETH-SOL`. If a `pair` is provided in the path, no token pairs from the query parameter(s) are used (i.e. the path variable is not additional, it overrides the values in the query parameter). |

{% tabs %}
{% tab title="200: OK Prices successfully returned." %}
```javascript
{
    "BTC-USDC": {
		"prices": {
			"spiceai": "41818.02",
			"gemini": "41918.76"
		},
		"minPrice": "41818.02",
		"maxPrice": "41918.76",
		"meanPrice": "41868.39"
	}, "LTC-USDT" : {
		"prices": {
			"coinbase": "128.07",
			"spiceai": "129.12"
		},
		"minPrice": "128.07",
		"maxPrice": "129.12",
		"meanPrice": "128.595"
	}, "ETH-BTC": { 
    "prices": {
			"coinbase": "3108.88",
			"gemini": "3132.97"
		},
		"minPrice": "3108.88",
		"maxPrice": "3132.97",
		"meanPrice": "3120.925"
	}
}
```
{% endtab %}
{% endtabs %}

## Historical Prices

The **`/v1/prices/historical/{pair}`** API returns historical prices of the specified token/currency pair(s).

## Get Historical Prices

<mark style="color:blue;">`GET`</mark> `https://data.spiceai.io/v1/prices/historical/{pair}`

Returns historical prices of the specified token/currency pair(s).

Providing both `start` and `end` will return all prices between the two timestamps at the provided `granularity`, however this must not be more than 10,000 prices.

If no `start` or `end` is provided then the 10 most recent prices based on the provided `granularity` will be returned.

If only `start` is provided then the next 10 subsequent prices after `start` will be returned. If only `end` is provided then the 10 most recent prices before `end` will be returned.

#### Path Parameters

| Name | Type   | Description                                                                                                                                           |
| ---- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| pair | String | One currency/token pair symbols. Always upper-case. e.g. `BTC-ETH`, `ETH-SOL`. Multiple pairs can be provided by query parameters instead, see below. |

#### Query Parameters

| Name        | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                              |
| ----------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| pairs       | String | One or more currency/token pairs symbols. Always upper-case. e.g. `BTC-ETH`, `ETH-SOL`. Multiple pairs can be provided in any of the following formats: `?pairs=BTC-ETH,ETH-SOL` or `?pairs=BTC-ETH&pairs=ETH-SOL`. If a `pair` is provided in the path, no token pairs from the query parameter(s) are used (i.e. the path variable is not additional, it overrides the values in the query parameter). |
| start       | Int    | UNIX timestamp of the start of the range to retrieve historical prices, cannot be before 12 months ago                                                                                                                                                                                                                                                                                                   |
| end         | Int    | UNIX timestamp of the end of the range to retrieve historical prices, cannot be before 12 months ago                                                                                                                                                                                                                                                                                                     |
| granularity | String | <p>Duration between each price returned (e.g.</p><p><code>5m</code></p><p>,</p><p><code>1h</code></p><p>,</p><p><code>7d</code></p><p>), default is</p><p><code>5m</code></p>                                                                                                                                                                                                                            |

{% tabs %}
{% tab title="200: OK Prices successfully returned." %}
```javascript
{
  "BTC-USD": [
    {
      "timestamp": "2023-03-15T15:45:00Z",
      "price": 24629.61,
      "high": 24652.55,
      "low": 24500,
      "open": 24514.67,
      "close": 24629.61
    },
    {
      "timestamp": "2023-03-15T15:50:00Z",
      "price": 24632.81,
      "high": 24726.31,
      "low": 24581.55,
      "open": 24589.89,
      "close": 24632.81
    },
    {
      "timestamp": "2023-03-15T15:55:00Z",
      "price": 24586.4,
      "high": 24721.65,
      "low": 24520,
      "open": 24706.59,
      "close": 24586.4
    },
    {
      "timestamp": "2023-03-15T16:00:00Z",
      "price": 24529.87,
      "high": 24578.71,
      "low": 24443.34,
      "open": 24515.43,
      "close": 24529.87
    }
  ], 
  "FLOW-USDT": [
    {
        "timestamp": "2023-09-18T00:05:00Z",
        "price": 0.441,
        "high": 0.445,
        "low": 0.436,
        "open": 0.436,
        "close": 0.441
    },
    {
        "timestamp": "2023-09-18T00:10:00Z",
        "price": 0.444,
        "high": 0.445,
        "low": 0.441,
        "open": 0.441,
        "close": 0.444
    },
    {
        "timestamp": "2023-09-18T00:15:00Z",
        "price": 0.44,
        "high": 0.443,
        "low": 0.439,
        "open": 0.443,
        "close": 0.44
    },
    {
        "timestamp": "2023-09-18T00:20:00Z",
        "price": 0.445,
        "high": 0.445,
        "low": 0.442,
        "open": 0.443,
        "close": 0.445
    },
  ]
}
```
{% endtab %}

{% tab title="400: Bad Request Bad request" %}
```javascript
{
    // Response
}
```
{% endtab %}

{% tab title="429: Too Many Requests Rate limit exceeded, slow down" %}
```javascript
{
    // Response
}
```
{% endtab %}

{% tab title="500: Internal Server Error Internal server error" %}
```javascript
{
    // Response
}
```
{% endtab %}
{% endtabs %}
