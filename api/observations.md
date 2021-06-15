# Observations

{% api-method method="get" host="https://api.spiceai.io" path="/v0.1/:org\_id/:app\_id/observations" %}
{% api-method-summary %}
Get Observations
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get observations.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="org\_id" type="string" required=true %}
Organization ID.
{% endapi-method-parameter %}

{% api-method-parameter name="app\_id" type="string" required=true %}
Application ID.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
API token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Observations successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find observations matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



