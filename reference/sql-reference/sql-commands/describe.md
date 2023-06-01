---
description: >-
  The DESCRIBE TABLE command is used to provide high-level information regarding
  the overall column properties of an existing dataset.
---

# DESCRIBE

Spice `DESCRIBE` supports all filesystem source types and relies upon a user’s existing privileges to access and describe a table or view.

### Syntax

#### Parameters <a href="#parameters-2" id="parameters-2"></a>

* \<table\_name> `String`   The name of an existing user-defined table.

**Examples**

{% code title="DESCRIBE TABLE syntax." %}
```sql
DESCRIBE TABLE table_name;
```
{% endcode %}

{% code title="Describing a table" %}
```sql
DESCRIBE TABLE eth.blocks;
```
{% endcode %}

Once a table or view has been queried, the Spice UI displays the following:

* Column headers indicating the type of information being described.
* Rows describing each table column.
* Data types, properties, policies, and other associated attributes

<table><thead><tr><th width="171">COLUMN_NAME</th><th width="206">DATA_TYPE</th><th>IS_NULLABLE</th><th>NUMERIC_PRECISION</th><th>NUMERIC_SCALE</th><th>EXTENDED_PROPERTIES</th><th>MASKING_POLICY</th></tr></thead><tbody><tr><td>number</td><td>BIGINT</td><td>YES</td><td>64</td><td>0</td><td>[]</td><td>[]</td></tr><tr><td>hash</td><td>CHARACTER VARYING</td><td>YES</td><td>NULL</td><td>NULL</td><td>[]</td><td>[]</td></tr><tr><td>parent_hash</td><td>CHARACTER VARYING</td><td>YES</td><td>NULL</td><td>NULL</td><td>[]</td><td>[]</td></tr><tr><td>nonce</td><td>CHARACTER VARYING</td><td>YES</td><td>NULL</td><td>NULL</td><td>[]</td><td>[]</td></tr><tr><td>sha3_uncles</td><td>CHARACTER VARYING</td><td>YES</td><td>NULL</td><td>NULL</td><td>[]</td><td>[]</td></tr><tr><td>logs_bloom</td><td>CHARACTER VARYING</td><td>YES</td><td>NULL</td><td>NULL</td><td>[]</td><td>[]</td></tr></tbody></table>

The cells containing a ‘\[]’ indicate “empty” values.

#### &#x20;<a href="#parameters-2" id="parameters-2"></a>
