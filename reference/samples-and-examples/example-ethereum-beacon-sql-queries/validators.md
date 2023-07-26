# Validators

### Recently updated validators, with their balance and status

**Typical query time**: < 2 seconds

```sql
SELECT validator_index, 
       balance_gwei / 1e9 as balance_eth, 
       status, 
       TO_TIMESTAMP(updated_at) as updated_at_time
FROM eth.beacon.validators
ORDER BY updated_at DESC
LIMIT 10
```

### Number of validators, grouped by status

**Typical query time**: < 2 seconds

```sql
SELECT COUNT(1) as num_validators, status
FROM eth.beacon.validators
GROUP BY status
ORDER BY COUNT(1) DESC
```

### Validator with the highest balance

**Typical query time**: < 15 seconds

```sql
SELECT validator_index, 
       balance_gwei / 1e9 AS balance_eth, 
       status, 
       TO_TIMESTAMP(updated_at) AS updated_at_time
FROM eth.beacon.validators
WHERE balance_gwei = (
    SELECT max(balance_gwei) AS max_balance
    FROM eth.beacon.validators
)
```

### ENS Domain Names that map to a validator

**Typical query time**: < 30 seconds

```sql
SELECT ens.names, ens.eth_address, bls.validator_index, status, balance_gwei / 1e9 AS balance_eth
FROM eth.beacon.bls_to_execution_changes AS bls
LEFT JOIN eth.beacon.validators AS val ON val.validator_index = bls.validator_index
LEFT JOIN (
    SELECT eth_address, LISTAGG(name, ',') WITHIN GROUP (ORDER BY name) AS "names"
    FROM ens.domains
    GROUP BY eth_address
) AS ens ON ens.eth_address = bls.to_execution_address
WHERE ens.names != ''
ORDER BY balance_gwei DESC
LIMIT 100
```
