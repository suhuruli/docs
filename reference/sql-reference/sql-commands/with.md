# WITH

The `WITH` clause defines a common table expression (CTE), which is a temporary named result set. The definition of a CTE includes its name, an optional list of column names, and a query expression (that is, a `SELECT` statement).

For more information about `SELECT` statements, see [SELECT](broken-reference).

### Syntax

{% code title="Example" %}
```sql
[ WITH <cte_name> [ ( <cte_column1>, <cte_column2>, ... ) ]
    AS ( <query> ) 
]
SELECT ...
```
{% endcode %}

### Parameters <a href="#parameters" id="parameters"></a>

\[ WITH \<cte\_name> \[ ( \<cte\_column1>, \<cte\_column2>, ... ) ] AS ( \<query> ) ] `String`&#x20;

A temporary named result set for use in the statement that defines the CTE.

* `<cte_name>`: The name of the CTE you are defining. The CTE must have a unique name within a given query.
* `<cte_column#>`: The names of the columns from the query that defines the CTE.
* `AS <query>`: The query (`SELECT`) statement that defines the CTE.

### Examples <a href="#examples" id="examples"></a>

{% code title="Query an existing table using a CTE clause." %}
```sql
WITH cte_quantity (Total)
  AS (
      SELECT SUM(transaction_count) as Total
      FROM eth.recent_blocks  WHERE transaction_count > 2
      GROUP BY pickup_datetime
      )
SELECT AVG(Total) average_pass
FROM cte_quantity
```
{% endcode %}

\
