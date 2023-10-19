---
description: Ethereum Gas Fees API documentation
---

# Gas Fees

The **`/eth/v1/gasfees`** API returns an estimate of the next block gas fees in Gwei.

It determines this based on the calculated next block base fee and a linear regression prediction based on the last 5 blocks of fees.

{% swagger baseUrl="https://data.spiceai.io" path="/eth/v1/gasfees" method="get" summary="Get Gas Fee Estimates" %}
{% swagger-description %}
Returns an estimate of the next block Ethereum gas fees.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="false" %}
API key for higher rate limits.
{% endswagger-parameter %}

{% swagger-response status="200" description="Gas fees successfully returned." %}
```
{
	"time": 1641347300,
	"lastBlock": 13942618,
	"nextBlockBaseFee": 74.813667468,
	"slow": 82,
	"normal": 83,
	"fast": 85,
	"instant": 88
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit exceeded. Higher rate limits can be obtained using an API key." %}
```
{
    "message": "Rate limit exceeded."
}
```
{% endswagger-response %}
{% endswagger %}

The **`/eth/v1/gasfees?price=usd`** API returns an estimate of the next block gas fees in Gwei and the current price in the specified currency or token.

{% swagger method="get" path="/eth/v1/gasfees?price=usd" baseUrl="https://data.spiceai.io" summary="Get Gas Fee Estimates With Price" %}
{% swagger-description %}
Returns an estimate of the next block Ethereum gas fees with price in the given currency or token.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="false" %}
API key for higher rate limits.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="price" required="true" %}
Currency or token for pricing conversion.

Currently support USD.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Gas fees successfully returned." %}
```javascript
{
	"time": 1641347526,
	"lastBlock": 13942641,
	"nextBlockBaseFee": 112.651926799,
	"ethPrice": 3794.462922013826,
	"slow": {
		"gwei": 116,
		"price": 9.205630794448966
	},
	"normal": {
		"gwei": 110,
		"price": 8.772699898734457
	},
	"fast": {
		"gwei": 105,
		"price": 8.351644878832529
	},
	"instant": {
		"gwei": 15,
		"price": 1.1621249972558882
	}
}
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit exceeded. Higher rate limits can be obtained using an API key." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

The `/eth/v1/gasfees?period=1d` API returns the historical gas used ratio and gas fees **by block** over the specified time period. If a period is not specified, it will default to 24 hours.

{% swagger method="get" path="/eth/v1/gasfees?period=1d" baseUrl="https://data.spiceai.io" summary="Get Historical Gas Used and Fees by Block" %}
{% swagger-description %}
Returns historical gas used and fees over time.

One of `start` or `period` is required.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="false" %}
API key for higher rate limits.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start" required="false" %}
The beginning of the historical period. Will default to 24h ago if not provided.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="period" required="false" %}
The period specified as a

[Duration Literal](../../getting-started/core-concepts/duration-literals.md)

. E.g. 5d. If not specified, will default from start until now, or 24 hours if start is also not provided.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="granularity" required="false" %}
The granularity of aggregation specified as a

[Duration Literal](../../getting-started/core-concepts/duration-literals.md)

. E.g. 1d. If not specified, fees per block will be provided.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Gas fees successfully returned." %}
```javascript
[
	{
		"time": 1638389086,
		"gasUsedRatio": 0.6453722692350096,
		"slow": 7,
		"normal": 32,
		"fast": 41,
		"instant": 68
	},
	{
		"time": 1638389108,
		"gasUsedRatio": 0.32565033107924796,
		"slow": 7,
		"normal": 24,
		"fast": 40,
		"instant": 205
	},
	{
		"time": 1638389118,
		"gasUsedRatio": 0.22219037765676844,
		"slow": 7,
		"normal": 38,
		"fast": 40,
		"instant": 72
	},
	{
		"time": 1638389126,
		"gasUsedRatio": 0.6348086333333334,
		"slow": 9,
		"normal": 35,
		"fast": 41,
		"instant": 51
	},
	{
		"time": 1638389140,
		"gasUsedRatio": 0.11676238513575173,
		"slow": 11,
		"normal": 11,
		"fast": 22,
		"instant": 79
	}
]
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit exceeded. Higher rate limits can be obtained using an API key." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

The `/eth/v1/gasfees?period=1w&granularity=1d` API returns the historical gas used ratio and gas fees **by time granularity** over the specified time period. If a period is not specified, it will default to 24 hours.

{% swagger method="get" path="/eth/v1/gasfees?period=7d&granularity=1d" baseUrl="https://data.spiceai.io" summary="Get Historical Gas Used and Fees by Time Granularity" %}
{% swagger-description %}
Returns historical gas used and fees over time.

One of `start` or `period` is required. `granularity` is required.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="false" %}
API key for higher rate limits.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start" required="false" %}
The beginning of the historical period. Will default to 24h ago if not provided.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="period" required="false" %}
The period specified as a

[Duration Literal](../../getting-started/core-concepts/duration-literals.md)

. E.g. 5d. If not specified, will default from start until now, or 24 hours if start is also not provided.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="granularity" required="true" %}
The granularity of aggregation specified as a

[Duration Literal](../../getting-started/core-concepts/duration-literals.md)

. E.g. 1d. If not specified, fees per block will be provided.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Gas fees successfully returned." %}
```javascript
[
	{
		"time": 1638389086,
		"gasUsedRatio": 0.6453722692350096,
		"slow": 7,
		"normal": 32,
		"fast": 41,
		"instant": 68
	},
	{
		"time": 1638389108,
		"gasUsedRatio": 0.32565033107924796,
		"slow": 7,
		"normal": 24,
		"fast": 40,
		"instant": 205
	},
	{
		"time": 1638389118,
		"gasUsedRatio": 0.22219037765676844,
		"slow": 7,
		"normal": 38,
		"fast": 40,
		"instant": 72
	},
	{
		"time": 1638389126,
		"gasUsedRatio": 0.6348086333333334,
		"slow": 9,
		"normal": 35,
		"fast": 41,
		"instant": 51
	},
	{
		"time": 1638389140,
		"gasUsedRatio": 0.11676238513575173,
		"slow": 11,
		"normal": 11,
		"fast": 22,
		"instant": 79
	}
]
```
{% endswagger-response %}

{% swagger-response status="429: Too Many Requests" description="Rate limit exceeded. Higher rate limits can be obtained using an API key." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
