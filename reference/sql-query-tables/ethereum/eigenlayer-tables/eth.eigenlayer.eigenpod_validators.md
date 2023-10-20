# eth.eigenlayer.eigenpod\_validators

* This is the validator list, filtered to just the validators that have withdrawal\_credentials that match one of the deployed eigenpods.

It is a view defined as:

```sql
SELECT * FROM goerli.beacon.validators val
WHERE val.withdrawal_credentials IN (
  select withdrawal_credential from eth.eigenlayer.eigenpods
)
```

See [goerli.beacon.validators](https://docs.spice.ai/reference/sql-query-tables/ethereum/beacon-chain-tables/eth.beacon.validators) for the schema and column definitions.
