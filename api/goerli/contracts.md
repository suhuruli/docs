---
description: Goerli Contracts API
---

# Contracts

The **`/goerli/v1/contracts`** API returns a list of known contract names and addresses.

{% swagger method="get" path="/goerli/v1/contracts" baseUrl="https://data.spiceai.io" summary="Get Contracts" %}
{% swagger-description %}
Returns a list of known contracts with their name, address, and tx hash.
{% endswagger-description %}

{% swagger-response status="200: OK" description="Contracts successfully returned." %}
```javascript
[
	{
		"name": "$Trolls",
		"address": "0xf044dc9431107f9c7d3bdbb8decfa51c315b77ae",
		"txHash": "0x159a12f1baa255a8eea0f0aec1996a13fec120ccd9b0e2fc6ac352bb1cff6039"
	},
	{
		"name": "A51SpacePass",
		"address": "0xeefba5763c798ca53d9b3426d900bca1fa45d27f",
		"txHash": "0x73405a42f4ededf63918d137c211911c522300f2bd53e56e0cb04c3fad7862f5"
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

{% swagger method="get" path="/goerli/v1/contracts/{contract_name}" baseUrl="https://data.spiceai.io" summary="Get Contract" %}
{% swagger-description %}
Returns the known contract with the given name.
{% endswagger-description %}

{% swagger-parameter in="path" name="contract_name" required="true" %}
The contract name.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Contract successfully returned." %}
```javascript
{
	"name": "UniswapV3Helper",
	"address": "0x0dca1a3f48407686da05f50ca6a59a16931aa81d",
	"txHash": "0x5b0b2eb5c5ba5ad89a274e2363b62cb6d788a4aa05116d79e53c930268f636ca"
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
