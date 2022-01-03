---
description: Health API documentation
---

# Health

The health API can be called to confirm availability.

{% swagger method="get" path="/health" baseUrl="https://api.spiceai.io" summary="Get API Health" %}
{% swagger-description %}
This endpoint gets the health of the API.
{% endswagger-description %}

{% swagger-response status="200: OK" description="The API is healthy." %}
```javascript
ok

```
{% endswagger-response %}
{% endswagger %}
