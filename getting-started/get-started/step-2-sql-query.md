# Step 2 - SQL Query

### Make a basic SQL query in the Playground

Use the Spice.xyz [Playground](broken-reference) to experiment with SQL queries, APIs, and models directly in app.&#x20;

It includes:

* A [SQL Query Editor](../../portal/sql-query-editor.md) for experimentation.
* Interactive API clients and sample code.

<figure><img src="../../.gitbook/assets/Screen Recording 2023-06-21 at 6.08.06 PM.gif" alt=""><figcaption></figcaption></figure>

### Make a basic SQL query using cURL

Once you've set up a [Portal account](portal-login.md), replace `[API-KEY]` in the sample below with your API Key from the Spice app.

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

{% hint style="info" %}
Visit the [FAQ](../../faq.md) page for more details.
{% endhint %}
