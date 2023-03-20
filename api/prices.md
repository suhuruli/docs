---
description: Prices HTTP API documentation
---

# Prices API

## Spot Prices

The **`/v0.1/prices`** API returns the spot prices of popular token/currency pairs for several exchanges, such as Coinbase, and Gemini, and the min, max, and average price across them.

{% swagger method="get" path="/v0.1/prices" baseUrl="https://data.spiceai.io" summary="Get Exchange Prices" %}
{% swagger-description %}
Returns token/currency pairs for several exchanges, such as Coinbase, and Gemini and the min, max, and average price across them.
{% endswagger-description %}

{% swagger-response status="200: OK" description="Prices successfully returned." %}
```javascript
[
	{
		"pair": "BTCUSD",
		"prices": {
			"coinbase": "41818.02",
			"gemini": "41918.76"
		},
		"minPrice": "41818.02",
		"maxPrice": "41918.76",
		"meanPrice": "41868.39"
	},
	{
		"pair": "LTCUSD",
		"prices": {
			"coinbase": "128.07",
			"gemini": "129.12"
		},
		"minPrice": "128.07",
		"maxPrice": "129.12",
		"meanPrice": "128.595"
	},
	{
		"pair": "ETHUSD",
		"prices": {
			"coinbase": "3108.88",
			"gemini": "3132.97"
		},
		"minPrice": "3108.88",
		"maxPrice": "3132.97",
		"meanPrice": "3120.925"
	},
	{
		"pair": "LRCUSD",
		"prices": {
			"coinbase": "1.4611",
			"gemini": "1.47834"
		},
		"minPrice": "1.4611",
		"maxPrice": "1.47834",
		"meanPrice": "1.46972"
	}
]
```
{% endswagger-response %}
{% endswagger %}

The **`/v0.1/prices/[pair]`** API returns spot prices of the specified token/currency pair.

E.g. `/v0.1/prices/btc-aud` will return the price of BTC in AUD.

The API will default to **USD** as the base currency if one is not provided.

E.g. `/v0.1/prices/btc` will return the price of BTC in USD.

{% swagger method="get" path="/v0.1/prices/[pair]" baseUrl="https://data.spiceai.io" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="pair" required="true" %}
The currency/token pair
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Prices for the pair successfully returned." %}
```javascript
{
	"pair": "ETH-AUD",
	"prices": {
		"coinbase": "2405.566348377514821804",
		"gemini": ""
	},
	"minPrice": "2405.566348",
	"maxPrice": "2405.566348",
	"avePrice": "2405.566348"
}
```
{% endswagger-response %}
{% endswagger %}

## Historical Prices (Preview)

The **`/v0.1/prices/[pair]`** API returns historical prices of the specified token/currency pair.

**NOTE: This method is in Preview. It's definition may change in non-backwards compatible ways.**

{% swagger method="get" path="/v0.1/prices/[pair]?preview=true" baseUrl="https://data.spiceai.io" summary="Get Historical Prices" %}
{% swagger-description %}
Returns historical prices of the specified token/currency pair.

Providing both `start` and `end` will return all prices between the two timestamps at the provided `granularity`, however this must not be more than 10,000 prices.

If no `start` or `end` is provided then the 10 most recent prices based on the provided `granularity` will be returned.&#x20;

If only `start` is provided, then `end` will default to the current UNIX timestamp. If only `end` is provided then the 10 most recent prices before `end` will be returned.
{% endswagger-description %}

{% swagger-parameter in="path" name="pair" type="String" %}
The token/currency pair to return prices for
{% endswagger-parameter %}

{% swagger-parameter in="query" name="preview" type="Bool" required="true" %}
Must be present and set to 

`true`

 to retrieve historical prices
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start" type="Int" %}
UNIX timestamp of the start of the range to retrieve historical prices, cannot be before 12 months ago
{% endswagger-parameter %}

{% swagger-parameter in="query" name="end" type="Int" %}
UNIX timestamp of the end of the range to retrieve historical prices, cannot be before 12 months ago
{% endswagger-parameter %}

{% swagger-parameter in="query" name="granularity" type="String" %}
Duration between each price returned (e.g. 

`5m`

, 

`1h`

, 

`7d`

), default is 

`5m`
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Prices successfully returned." %}
```javascript
{
  "pair": "BTC-USD",
  "prices": [
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
    },
    {
      "timestamp": "2023-03-15T16:05:00Z",
      "price": 24460.3,
      "high": 24584,
      "low": 24396.8,
      "open": 24534.23,
      "close": 24460.3
    },
    {
      "timestamp": "2023-03-15T16:10:00Z",
      "price": 24427.57,
      "high": 24528.9,
      "low": 24388,
      "open": 24415.61,
      "close": 24427.57
    },
    {
      "timestamp": "2023-03-15T16:15:00Z",
      "price": 24311.13,
      "high": 24431.47,
      "low": 24183.75,
      "open": 24411.63,
      "close": 24311.13
    },
    {
      "timestamp": "2023-03-15T16:20:00Z",
      "price": 24376.97,
      "high": 24394.36,
      "low": 24250,
      "open": 24286.56,
      "close": 24376.97
    },
    {
      "timestamp": "2023-03-15T16:25:00Z",
      "price": 24345.7,
      "high": 24428.51,
      "low": 24287.47,
      "open": 24295.9,
      "close": 24345.7
    },
    {
      "timestamp": "2023-03-15T16:30:00Z",
      "price": 24369.92,
      "high": 24393.88,
      "low": 24283.84,
      "open": 24329.97,
      "close": 24369.92
    }
  ]
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Bad request" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit exceeded, slow down" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
