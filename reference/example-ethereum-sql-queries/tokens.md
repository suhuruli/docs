# Tokens

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
