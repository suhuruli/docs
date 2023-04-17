---
description: >-
  The SELECT statement is used to select data from a database. Spice supports
  querying using standard SELECT statements.
---

# SELECT

### Syntax

{% code title="SELECT example" %}
```sql
[ WITH ... ] 
SELECT [ ALL | DISTINCT ] 

  {
    { * | <column_name1>, <column_name2>, ... } FROM { <table_name> ) }
    [ { PIVOT | UNPIVOT } ( <expression> ) ]
    [ JOIN <expression> ]
    [ WHERE <condition> ]
    [ GROUP BY <expression> ]
    [ QUALIFY <expression> ]
    [ ORDER BY <column_name1>, <column_name2>, ... [ DESC ] ]
    [ LIMIT <count> ]
  }
```
{% endcode %}

#### Parameters <a href="#parameters" id="parameters"></a>

* `[ WITH ...] String` \<Optional> Defines a common table expression (CTE), which is a named subquery. For more information, read [WITH](with.md).&#x20;
* `[ ALL | DISTINCT ]`  `String`   \<Optional> Specifies the result set that is returned. Similar to the asterisk (\*), `ALL` returns all the values in the result set. `DISTINCT` eliminates duplicates from the result set. If you do not specify an option, the default is `ALL`.&#x20;
* \*  Indicates that you want to query all columns in the table.
* `<column_name1>, <column_name2>, ...`   `String` The name of the column(s) that you want to query.
* { \<table\_name> } `String` The path to the source that you want to query a table in.&#x20;
* { PIVOT | UNPIVOT } ( \<expression> ) `String`  `PIVOT` \<Optional> converts a set of data from rows into columns. `UNPIVOT` converts a set of data from columns into rows. The expression can be one of the following:
  * pivot\_clause: The query to aggregate the data on.
  * pivot\_for\_clause: Which columns to group and pivot on.
  * pivot\_in\_clause: Filters the values for the columns _pivot\_for\_clause_. Each of the values in this clause will be a separate column.
  * **Note**: This keyword is applied to a `SELECT` statement. The syntax does not support an alias between the table/subquery and either the `PIVOT` or `UNPIVOT` clause. For example, `SELECT name, dept FROM employees) <alias> PIVOT <query>` is not supported.
* JOIN \<expression> `Boolean`  \<Optional> Combines rows from two tables or views to create a new combined row that can be used in the query. Supported expressions are `LEFT [OUTER] JOIN`, `RIGHT [OUTER] JOIN`, `FULL [OUTER] JOIN`, `INNER JOIN`, `CROSS JOIN`.
* WHERE \<condition> `String`  \<Optional> Use the `WHERE` clause to filter your query and extract only the records that fulfill a specified condition. The following operators can be used: `+`, `>`, `<`, `>=`, `<`=, { `<>` | `!=` }, `BETWEEN`, `LIKE`, `IN`. Additionally, `<condition>` can include logical operators, such as `AND`, `OR`, and `NOT`.
* GROUP BY \<expression> `String`  \<Optional> Groups rows with the same group-by-item expressions and computes aggregate functions (such as `COUNT()`, `MAX()`, `MIN()`, `SUM()`, `AVG()` ) for the resulting group. A `GROUP BY` expression can be one or more column names, a number referencing a position in the `SELECT` list, or a general expression.
* QUALIFY \<expression> `Boolean` \<Optional> Filters the results of window functions. To use QUALIFY, at least one window function must be present in either the SELECT statement or within the QUALIFY expression. The expression filters the result after aggregates and window functions are computed; it can also contain window functions. The boolean expression can be the result of a subquery.
* ORDER BY \<column\_name1>, \<column\_name2>, … \[ DESC ] `String` \<Optional> Sort the result by a specific column. By default, the records are sorted in ascending order. Use `DESC` to sort the records in descending order.
* LIMIT \<count> `Integer` \<Optional> Constrains the maximum number of rows returned by the query. Must be a non-negative integer.
