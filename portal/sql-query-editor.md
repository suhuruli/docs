---
description: Use the Playground's SQL editor to easily explore data
---

# SQL Query Editor

<figure><img src="../.gitbook/assets/Screenshot 2023-10-24 at 12.16.04 AM.png" alt=""><figcaption><p>Spice.ai Query Editor</p></figcaption></figure>

Open the SQL editor by navigating to an app and clicking **SQL Query** in the sidebar.

### SQL table, column, and keyword suggestions

The Spice.ai Query Editor will suggest table and column names along with keywords as you type. You can manually prompt for a suggestion by pressing **ctrl+space**.

1. Start typing a SQL command, such as `SELECT * FROM`
2. As you type, the Query Editor will suggest possible completions based on the query context. You can use the arrow keys or mouse to select a completion, and then press **Enter** or **Tab** to insert it into the editor.

Examples of using the SQL suggestions:

* Select the `btc.blocks` table:
  * Type `SELECT * FROM btc` and press Tab. The editor will suggest `btc.blocks` as a possible table. Press Enter to insert it into the query.

<figure><img src="../.gitbook/assets/Screenshot 2023-10-24 at 12.23.05 AM.png" alt=""><figcaption><p>A list of datasets available in Spice</p></figcaption></figure>

* Show the fields in the `eth.recent_blocks` table:
  * Type `SELECT * FROM eth.recent_blocks WHERE "`. The editor will list the fields in the table.

<figure><img src="../.gitbook/assets/Screenshot 2023-10-24 at 12.25.29 AM.png" alt=""><figcaption><p>The available fields for <code>eth.recent_blocks</code> along with their type.</p></figcaption></figure>

### AI SQL Completion (Preview)

<figure><img src="../.gitbook/assets/SQL Autocompletion new UI-2.gif" alt=""><figcaption><p>Use AI to help you write your Spice SQL queries.</p></figcaption></figure>

1. Ensure the **AI SQL Completion** button is toggled on.
2. Write a SQL comment describing your desired query:\
   E.g. `-- Return the Ethereum block number that had the most cumulative gas fees paid from the past hour`
3. Press **Enter** to move the cursor to the next line - this will trigger the auto-completion. It may take a few seconds to generate.
4. Press **Tab** to accept the AI-generated completion.

<figure><img src="../.gitbook/assets/Screenshot 2023-01-11 at 7.28.38 PM.png" alt=""><figcaption><p>AI generated query recommendation</p></figcaption></figure>

### Chart Playground (Preview)

Chart Playground is an in-browser charting interface to quickly generate visualizations from queried data, such as **time-series trends, variable relationships, and data distributions**.

1. Click the chart bar icon to access the Chart Playground and view a **recommended chart** upon entry.
2. Use dropdown menus to change x-axis, y-axis, chart style. **Bar, line, dot** chart style are currently supported. Choosing only x or only y will default to a "bar style" distribution plot.
3. **Resize** the chart by dragging the **handles** at the top and right.
4. Download the chart by clicking the **download button** in the top-right corner.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>Chart Playground Overview</p></figcaption></figure>

{% hint style="warning" %}
The Chart Playground relies on an [in-browser DuckDB instance](https://uwdata.github.io/mosaic/core/#mosaic-core) with limited capacity. Try to reduce the size of the data if no chart is displayed.
{% endhint %}

### AI Charting (Preview)

AI Charting is a **conversational** chart interface that offers an **AI-enhanced** experience for visualizing queried data.

By asking a question about queried data, an **interactive chart** will be generated.

1. Click the chat bubble icon to enter the AI Charting interface.
2. Enter a question of the queried data in the input box. **Specify variables and styles** to get most ideal chart result. Hit enter or click submit button to generate the chart.
3. Utilize interactive features including **hovering, zooming, box-select**, etc.
4. If a question entered is not valid for the data, a recommended question will be shown. Click and try the recommended question or ask another question to generate a new chart.

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption><p>Overview of AI Charting</p></figcaption></figure>

{% hint style="warning" %}
Chart generation may fail if the question requires complex data manipulation or is not relevant to the data, as shown below.
{% endhint %}

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption><p>Chart generation failure due to invalid question.</p></figcaption></figure>
