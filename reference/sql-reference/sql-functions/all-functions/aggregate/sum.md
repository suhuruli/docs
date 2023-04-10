---
description: Returns the sum of non-NULL input expressions.
---

# SUM

### Syntax <a href="#syntax" id="syntax"></a>

#### SUM(_column\_name_ number or interval) → same as input <a href="#sumcolumn_name-number-or-interval--same-as-input" id="sumcolumn_name-number-or-interval--same-as-input"></a>

* column\_name: The column containing the values to sum.

**Examples**

<pre class="language-sql" data-title="Aggregate function example"><code class="lang-sql">SELECT SUM(trip_distance_mi) 
FROM eth.recent_blocks
<strong>-- 9.858134477692287E8
</strong></code></pre>

{% code title="Window function example" %}
```sql
SELECT "tip_amount", "fare_amount", SUM("total_amount") 
OVER (partition by "tip_amount") as "sum_amount" 
FROM eth.recent_blocks 
LIMIT 1
-- tip_amount, fare_amount, sum_amount
-- -51.0, -4.0, -56.0
```
{% endcode %}
