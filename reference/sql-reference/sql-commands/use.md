# USE

The `USE` command enables you to specify the context to be used for the current query session. After you issue this command, your queries do not need to specify the path of the tables and views that they run against. When you want to query tables and views in a different path, you can run this command again with that path or add the path to your queries.

### Syntax

{% code title="USE Example" %}
```sql
USE <path> 
```
{% endcode %}

#### Parameter <a href="#parameter" id="parameter"></a>

* \<path> `String` The path that of the tables, views, or both that you want to query.

**Example**

{% code title="Use the demo source." %}
```sql
USE eth.recent_blocks 
```
{% endcode %}
