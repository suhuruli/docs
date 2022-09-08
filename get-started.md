---
description: Get started with Spice Data
---

# Getting started

Follow this guide to get started with Spice. <mark style="color:green;">An API key is not required!</mark>

### Call the API

Using your browser or cURL, call the [Gas Fees Estimates](broken-reference/) API as shown below. The response is a JSON object with an estimate of the next block's slow, normal, fast, and instant fees in Gwei.

{% tabs %}
{% tab title="Browser" %}
Navigate to [data.spiceai.io/eth/v0.1/gasfees](https://data.spiceai.io/eth/v0.1/gasfees).

Example:

{% embed url="https://data.spiceai.io/eth/v0.1/gasfees?price=USD" %}
Example results from the Ethereum gas fees API.
{% endembed %}
{% endtab %}

{% tab title="cURL" %}
```
curl https://data.spiceai.io/eth/v0.1/gasfees
```
{% endtab %}
{% endtabs %}

### Make a basic SQL query

{% tabs %}
{% tab title="cURL" %}
```bash
curl --request POST \
  --url 'https://data.spiceai.io/v0.1/sql' \
  --header 'Content-Type: text/plain' \
  --data 'select * from eth.recent_blocks order by "timestamp" desc'
```
{% endtab %}
{% endtabs %}

### Use an SDK

Use the [Python SDK](sdks/python-sdk.md) to query Spice using it's high-performance Apache Arrow transport.

TypeScript/JavaScript SDK coming soon!
