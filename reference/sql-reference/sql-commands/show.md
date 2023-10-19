# SHOW

### Syntax

{% code title="Showing a Table Example" %}
```sql
SHOW TABLE [ LIKE { pattern } ]
```
{% endcode %}

#### Parameters <a href="#parameters" id="parameters"></a>

* \[ LIKE ] The pattern match is case-insensitive but must be used with the LIKE operator.

#### Examples <a href="#examples" id="examples"></a>

{% code title="Show all existing tables." %}
```sql
SHOW TABLES;
```
{% endcode %}

{% code title="Show an existing table with the exact name." %}
```sql
SHOW TABLES LIKE 'eth.recent_blocks';
```
{% endcode %}

{% code title="Show all existing tables with names that start with protect_." %}
```sql
SHOW TABLES LIKE 'eth.recent_%';
```
{% endcode %}
