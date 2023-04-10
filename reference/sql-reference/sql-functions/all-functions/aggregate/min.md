---
description: Returns the minimum value among the non-NULL input expressions.
---

# MIN

### Syntax <a href="#syntax" id="syntax"></a>

#### MIN(_expression_ any primitive) → same as input <a href="#minexpression-any-primitive--same-as-input" id="minexpression-any-primitive--same-as-input"></a>

* expression: Input expression.

**Examples**

{% code title="Aggregate function example" %}
```sql
SELECT MIN("total_amount") 
FROM eth.recent_blocks

-- EXPR$0
-- -1430.0
```
{% endcode %}

#### MIN(_expression_ any primitive) → same as input <a href="#minexpression-any-primitive--same-as-input-1" id="minexpression-any-primitive--same-as-input-1"></a>

* expression: Input expression.

**Examples**

{% code title="Window function example" %}
```sql
SELECT "trip_distance_mi", 
  MIN("total_amount") OVER(PARTITION BY "trip_distance_mi") "min_total_amount"
FROM eth.recent_blocks
LIMIT 1

-- trip_distance_mi, min_total_amount
-- 0.06, -52.5
```
{% endcode %}

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

For information about the data types that are supported in Spice, see Data Types.
