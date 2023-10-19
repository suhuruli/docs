---
description: Ethereum Blocks API
---

# Blocks

The **`/eth/v1/blocks/range`** API returns the start and end block numbers for a given time range.

{% swagger method="get" path="/eth/v1/blocks/range?start=1643690381" baseUrl="https://data.spiceai.io" summary="Get Block Numbers By Time Range" %}
{% swagger-description %}
Returns the start and end block numbers by time range and the count of blocks in the range.

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

{% swagger-response status="200: OK" description="Block range successfully returned." %}
```javascript
{
	"startBlock": 14118049,
	"endBlock": 14119207,
	"numBlocks": 1159
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
