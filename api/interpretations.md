---
description: Gas Fees API documentation
---

# Gas Fees

{% swagger baseUrl="https://api.spiceai.io" path="/eth/v0.1/gasfees" method="get" summary="Get Get Fees" %}
{% swagger-description %}
This endpoint provides a prediction of the next block Ethereum gas fees.
{% endswagger-description %}

{% swagger-parameter in="query" name="key" %}
API key
{% endswagger-parameter %}

{% swagger-response status="200" description="Gas fees successfully returned." %}
```
{
    "time": 123,
    "slow": 64,
    "normal": 64,
    "fast": 64,
    "instant": 64
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

