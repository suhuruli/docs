---
description: Prices API documentation
---

# Prices API

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
