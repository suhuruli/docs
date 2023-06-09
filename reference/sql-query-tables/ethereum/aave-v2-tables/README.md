---
description: Ethereum Aave V2 tables available to query via SQL
---

# Aave V2 Tables

#### Tables available to query

| Name                                                           | Description                           |
| -------------------------------------------------------------- | ------------------------------------- |
| [`eth.aave_v2.loan_updates`](eth.aave\_v2.loans.md)            | All updates to aave v2 loans          |
| [`eth.aave_v2.collateral_updates`](eth.aave\_v2.collateral.md) | All updates to aave v2 collateral     |
| [`eth.aave_v2.loans`](eth.aave\_v2.loans.md)                   | Latest view of all aave v2 loans      |
| [`eth.aave_v2.collateral`](eth.aave\_v2.collateral.md)         | Latest view of all aave v2 collateral |

The columns and their schema available for each table can be viewed with the `describe <table>` command. For example:

```
DESCRIBE eth.aave_v2.loan_updates
DESCRIBE eth.aave_v2.collateral_updates
DESCRIBE eth.aave_v2.loans
DESCRIBE eth.aave_v2.collateral
```

**Improving query performance - indexed columns**

Query performance can be significantly improved by adding `WHERE` clauses to your query on specific indexed columns.

| Table Name                       | Indexed Columns |
| -------------------------------- | --------------- |
| `eth.aave_v2.loan_updates`       | `block_number`  |
| `eth.aave_v2.collateral_updates` | `block_number`  |

