# SQL Query Editor

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1).png" alt=""><figcaption><p>Spice.xyz Query Editor</p></figcaption></figure>

Open the SQL editor by navigating to an app and clicking **SQL Query** in the sidebar.

### AI SQL Completion (Preview)

{% embed url="https://youtu.be/UQ5cb6Nku3w" %}
Use AI to help you write your Spice SQL queries.
{% endembed %}

1. Ensure the **AI SQL Completion** button is toggled on.
2. Write a SQL comment describing your desired query: \
   E.g.  `-- Return the Ethereum block number that had the most cumulative gas fees paid from the past hour`
3. Press **Enter** to move the cursor to the next line - this will trigger the auto-completion. It may take a few seconds to generate.
4. Press **Tab** to accept the AI-generated completion.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-11 at 7.28.38 PM.png" alt=""><figcaption><p>AI generated query recommendation</p></figcaption></figure>

### SQL table, column, and keyword suggestions

The Spice.xyz Query Editor will suggest table and column names along with keywords as you type. You can manually prompt for a suggestion by pressing **ctrl+space**.

1. Start typing a SQL command, such as `SELECT * FROM`
2. As you type, the Query Editor will suggest possible completions based on the query context. You can use the arrow keys or mouse to select a completion, and then press **Enter** or **Tab** to insert it into the editor.

Examples of using the SQL suggestions:

* Select the `btc.blocks` table:
  * Type `SELECT * FROM btc` and press Tab. The editor will suggest `btc.blocks` as a possible table. Press Enter to insert it into the query.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-09 at 10.24.15 AM.png" alt=""><figcaption><p>A list of datasets available in Spice</p></figcaption></figure>

* Show the fields in the `eth.recent_blocks` table:
  * Type `SELECT * FROM eth.recent_blocks WHERE "`. The editor will list the fields in the table.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-09 at 10.27.43 AM.png" alt=""><figcaption><p>The available fields for <code>eth.recent_blocks</code> along with their type.</p></figcaption></figure>
