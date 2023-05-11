# WITH

The `WITH` clause defines a common table expression (CTE), which is a temporary named result set. The definition of a CTE includes its name, an optional list of column names, and a query expression (that is, a `SELECT` statement).

For more information about `SELECT` statements, see [SELECT](select.md).

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

<pre class="language-sql" data-title="Get Average ETH withdrawn per block after the Ethereum Shanghai Upgrade"><code class="lang-sql">with eth_withdrawn as (
  select eth.withdrawals.block_number, SUM(amount) as amount_gwei
  from eth.withdrawals
  group by eth.withdrawals.block_number
  order by block_number asc)
<strong>
</strong><strong>select AVG(amount_gwei / 1e9) as amount_eth
</strong>from eth_withdrawn
</code></pre>

\
