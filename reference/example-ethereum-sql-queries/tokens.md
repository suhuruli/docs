# Tokens

### Get Token Transfers with Token Standard

Get recent token transfers along with the token standard the token is using.

```sql
SELECT token_address, 
       token_standard, 
       from_address, 
       to_address, 
       token_id, 
       "value", 
       transaction_hash, 
       log_index, 
       block_number 
FROM eth.recent_token_transfers 
ORDER BY block_number DESC
LIMIT 10
```

### Get Tokens With Standard

Joins the tokens table with the contracts table to get information about the token standard that the token is using.

**Typical query time**: <20 seconds

```sql
SELECT DISTINCT tokens.symbol, tokens.name, is_erc721, is_erc20
FROM eth.tokens
INNER JOIN eth.contracts ON eth.contracts.address = eth.tokens.address
WHERE eth.tokens.name != ''
ORDER BY eth.tokens.name
```
