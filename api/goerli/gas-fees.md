---
description: Goerli Gas Fees API documentation
---

# Gas Fees

The **`/goerli/v1/gasfees`** API returns an estimate of the next block gas fees in Gwei.

It determines this based on the calculated next block base fee and a linear regression prediction based on the last 5 blocks of fees.

{% swagger baseUrl="https://data.spiceai.io" path="/goerli/v1/gasfees" method="get" summary="Get Gas Fee Estimates" %}
{% swagger-description %}
Returns an estimate of the next block Goerli gas fees.
{% endswagger-description %}

{% swagger-parameter in="query" name="api_key" required="false" %}
API key for higher rate limits.
{% endswagger-parameter %}

{% swagger-response status="200" description="Gas fees successfully returned." %}
```
{
	"time": 1641347300,
	"lastBlock": 8930280,
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
