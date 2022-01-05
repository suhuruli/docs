---
description: Ethereum Gas Fees API documentation
---

# Gas Fees



{% swagger baseUrl="https://data.spiceai.io" path="/eth/v0.1/gasfees" method="get" summary="Get Get Fee Estimates" %}
{% swagger-description %}
Returns an estimate of the next block Ethereum gas fees.


{% endswagger-description %}

{% swagger-parameter in="query" name="key" %}
API key
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



{% swagger method="get" path="/eth/v0.1/gasfees?price=usd" baseUrl="https://data.spiceai.io" summary="Get Gas Fee Estimates With Price" %}
{% swagger-description %}
Returns an estimate of the next block Ethereum gas fees with price in the given currency or token. 
{% endswagger-description %}

{% swagger-parameter in="query" name="key" %}
API
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
