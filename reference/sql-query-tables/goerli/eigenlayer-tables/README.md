---
description: Goerli EigenLayer tables available to query via SQL
---

# EigenLayer Tables

Learn about [EigenLayer](https://www.eigenlayer.xyz/) and read the [whitepaper](https://2039955362-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FPy2Kmkwju3mPSo9jrKKt%2Fuploads%2F2dCfPgItRfQbX25KriQv%2Fwhitepaper.pdf?alt=media\&token=d4d94480-3f01-4e63-bc92-a0658ea37aab).

#### Goerli EigenLayer tables available to query

| Table Name                                | Firecache Table Name                    | Description                                                               |
| ----------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------- |
| `goerli.eigenlayer.eigenpod_validators`   | `goerli_eigenlayer_eigenpods`           | All Eigenpods                                                             |
| `goerli.`eigenlayer.`eigenpod_validators` | `goerli_eigenlayer_eigenpod_validators` | All Eigenpod Validators                                                   |
| `goerli.`eigenlayer.`eigenpod_balances`   | `goerli_eigenlayer_eigenpod_balances`   | Eigenpod ETH wallet changed balances including the delta from last block  |
| `goerli.`eigenlayer.`withdrawal_router`   | `goerli_eigenlayer_withdrawal_router`   | Withdrawal Router ETH wallet balances including the delta from last block |

The table list is also available as a SQL query using `show tables`. For example:

```sql
SHOW TABLES IN goerli.eigenlayer
```

#### Examples

