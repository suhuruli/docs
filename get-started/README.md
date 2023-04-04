---
description: Get started with Spice Data
---

# Getting started

Follow this guide to get started with Spice.

### Call the API

Using your browser or cURL, call the [Gas Fees Estimates](../broken-reference/) API as shown below. The response is a JSON object with an estimate of the next block's slow, normal, fast, and instant fees in Gwei.

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

### Use an SDK

Use the [Python SDK](../sdks/python-sdk.md), [Node.js SDK](../sdks/node.js-sdk/), or [Go SDK](../sdks/go.md) to query Spice using it's high-performance Apache Arrow transport.
