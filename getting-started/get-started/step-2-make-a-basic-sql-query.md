# Step 3 - Make a basic SQL Query

### Make a basic SQL query

To get an API key, set up a [Portal account](portal-login.md).

{% tabs %}
{% tab title="cURL" %}
```bash
curl --request POST \
  --url 'https://data.spiceai.io/v0.1/sql' \
  --header 'Content-Type: text/plain' \
  --header 'X-API-KEY: [API-KEY]'
  --data 'select * from eth.recent_blocks order by "timestamp" desc'
```
{% endtab %}
{% endtabs %}

To get an API key, set up a [Portal account](portal-login.md).

Your API key also unlocks custom visualizations via [Grafana Plugin](../../integrations/grafana.md).&#x20;
