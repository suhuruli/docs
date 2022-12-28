---
description: Query web3 data with SQL via the HTTP API
---

# HTTP API

Blockchain and contract data may be queried by posting SQL to the `/v0.1/sql` API.

See [Tables](broken-reference/) for a list of tables to query or browse the example queries listed in the menu.

#### Requirements and limitations

* An API key is required for all SQL queries.
* Results are limited to 500 rows. Use the [Apache Arrow Flight API](broken-reference/) to fetch up to 1M rows in a single query or the [Async HTTP API](http-api-1.md) to fetch results with paging.
* Requests are limited to 90 seconds.

{% swagger method="post" path="/v0.1/sql" baseUrl="https://data.spiceai.io" summary="Perform a SQL query" %}
{% swagger-description %}
The SQL query should be sent in the body of the request as plain text
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="query" name="api_key" required="false" %}
The API Key for your Spice app
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
The API Key for your Spice app
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Query result" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="The query could not be parsed" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Missing the API Key" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```bash
curl --request POST \
  --url https://data.spiceai.io/v0.1/sql \
  --header 'Content-Type: text/plain' \
  --header 'X-API-Key: [api-key]' \
  --data 'select count(number) from eth.recent_blocks'
```
{% endtab %}

{% tab title="Javascript" %}
```javascript
const API_KEY = "[api-key]";

const query = `
select count(number) as num_blocks
from eth.recent_blocks
`;

const res = await fetch("https://data.spiceai.io/v0.1/sql", {
  method: "POST",
  headers: {
    "Content-Type": "text/plain",
    "X-API-Key": API_KEY,
  },
  body: query,
});

console.log(await res.json());
```
{% endtab %}
{% endtabs %}
