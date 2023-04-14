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

| COLUMN\_NAME | DATA\_TYPE        | IS\_NULLABLE | NUMERIC\_PRECISION | NUMERIC\_SCALE | EXTENDED\_PROPERTIES | MASKING\_POLICY |
| ------------ | ----------------- | ------------ | ------------------ | -------------- | -------------------- | --------------- |
| number       | BIGINT            | YES          | 64                 | 0              | \[]                  | \[]             |
| hash         | CHARACTER VARYING | YES          | NULL               | NULL           | \[]                  | \[]             |
| parent\_hash | CHARACTER VARYING | YES          | NULL               | NULL           | \[]                  | \[]             |
| nonce        | CHARACTER VARYING | YES          | NULL               | NULL           | \[]                  | \[]             |
| sha3\_uncles | CHARACTER VARYING | YES          | NULL               | NULL           | \[]                  | \[]             |
| logs\_bloom  | CHARACTER VARYING | YES          | NULL               | NULL           | \[]                  | \[]             |

The cells containing a ‘\[]’ indicate “empty” values.

#### &#x20;<a href="#parameters-2" id="parameters-2"></a>
