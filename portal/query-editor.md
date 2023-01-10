# Query Editor

To use the SQL query completion feature in the Spice cloud portal:

1. Open the SQL editor by navigating to an app and clicking the "SQL Query" sidebar item.
2. Start typing a SQL command, such as `SELECT * FROM`
3. As you type, the portal will suggest possible completions based on the query context. You can use the arrow keys or mouse to select a completion, and then press Enter or Tab to insert it into the editor.

Examples of using the SQL query completion feature:

* Select the `btc.blocks` table:
  * Type `SELECT * FROM btc` and press Tab. The editor will suggest `btc.blocks` as a possible completion. Press Enter to insert it into the query.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-09 at 10.24.15 AM.png" alt=""><figcaption><p>A list of datasets available in Spice</p></figcaption></figure>

* Show the fields in the `eth.recent_blocks` table:
  * Type `SELECT * FROM eth.recent_blocks WHERE "`. The editor will list the fields in the table.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-09 at 10.27.43 AM.png" alt=""><figcaption><p>The available fields for <code>eth.recent_blocks</code> along with their type.</p></figcaption></figure>
