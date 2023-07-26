---
description: Create, update, and manage Spicepods (beta)
---

# Spicepods API

A Spicepod is a package (a zip file) of data and AI configuration used by a Spice application.

A Spicepod manifest is a YAML file with Spice application configuration.

### APIs

**Upload a Spicepod**

{% swagger method="post" baseUrl="https://data.spiceai.io" expanded="false" path="/v0.1/orgs/{org_name}/apps/{app_id}/spicepods" summary="Upload a Spicepod" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="org_name" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="path" name="app_id" required="true" type="Number" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="Content" required="true" %}
Spicepod file content an an octect stream (zip)
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="" %}

{% endswagger-response %}
{% endswagger %}

#### List Spicepods

{% swagger method="get" path="/v0.1/orgs/{org_name}/apps/{app_id}/spicepods" baseUrl="https://data.spiceai.io" summary="List all Spicepods" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="org_name" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="path" name="app_id" required="true" type="Number" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="List of spicepods " %}

{% endswagger-response %}
{% endswagger %}

**Get a Spicepod**

{% swagger method="get" baseUrl="https://data.spiceai.io" expanded="false" path="/v0.1/orgs/{org_name}/apps/{app_id}/spicepods/{name}" summary="Get a Spicepod by name" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="org_name" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="path" name="app_id" required="true" type="Number" %}

{% endswagger-parameter %}

{% swagger-parameter in="path" name="name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Content of the spicepod " %}

{% endswagger-response %}
{% endswagger %}

**Delete a Spicepod**

{% swagger method="delete" path="/v0.1/orgs/{org_name}/apps/{app_id}/spicepods/{name}" baseUrl="https://data.spiceai.io" summary="Delete a Spicepod by name" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="org_name" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="path" name="app_id" required="true" type="Number" %}

{% endswagger-parameter %}

{% swagger-parameter in="path" name="name" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="204: No Content" description="" %}

{% endswagger-response %}
{% endswagger %}

### Limitations

* Maximum size of a Spicepod file is 1MB.
