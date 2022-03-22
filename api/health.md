---
description: Health HTTP API documentation
---

# Health API

The health API can be called to confirm the overall availability of the API service.

{% swagger method="get" path="/health" baseUrl="https://data.spiceai.io" summary="Get API Health" %}
{% swagger-description %}
This endpoint gets the health of the API.
{% endswagger-description %}

{% swagger-response status="200: OK" description="The API is healthy." %}
```javascript
ok
```
{% endswagger-response %}
{% endswagger %}
