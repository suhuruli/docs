---
description: Get started with Spice Data
---

# Getting started

Follow this guide to get started with Spice Data. <mark style="color:green;">An API key is not required!</mark>

## Call the API

Using your browser or cURL, call the [Gas Fees Estimates](api/interpretations/gas-fees.md#get-gas-fee-estimates) API as shown below. The response is a JSON object with an estimate of the next block slow, normal, fast, and instant fees in Gwei.

{% tabs %}
{% tab title="Browser" %}
Navigate to [data.spiceai.io/eth/v0.1/gasfees](https://data.spiceai.io/eth/v0.1/gasfees).



Example:

{% embed url="https://data.spiceai.io/eth/v0.1/gasfees" %}
Response from the Gas Fees API
{% endembed %}
{% endtab %}

{% tab title="cURL" %}
```
curl https://data.spiceai.io/eth/v0.1/gasfees
```
{% endtab %}
{% endtabs %}

