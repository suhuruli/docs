---
description: Returns the total number of records for the specified expression.
---

# COUNT

### Syntax <a href="#syntax" id="syntax"></a>

#### COUNT(_expression_ any primitive) → bigint <a href="#countexpression-any-primitive--bigint" id="countexpression-any-primitive--bigint"></a>

* expression: The expression to evaluate the number of records. This parameter can either be \* or a column name of any primitive data type. Using asterisk (\*) will include rows that contain `NULL`. Specifying a column name will ignore rows have `NULL` in that column.

**Examples**

{% code title="Aggregate function example" %}
```sql
SELECT COUNT(passenger_count) 
FROM eth.recent_blocks
-- 338293677
```
{% endcode %}

{% code title="Window function example" %}
```sql
SELECT "trip_distance_mi",
  COUNT("total_amount") 
  OVER(PARTITION BY "trip_distance_mi") "count_total_amount"
FROM eth.recent_blocks
LIMIT 1

-- trip_distance_mi, count_total_amount
-- 0.06, 61900
```
{% endcode %}
