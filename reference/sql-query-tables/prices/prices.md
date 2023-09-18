---
 description: SQL table schema for spiceai.prices
---
 
# Price data

Aggregated price data for all tokens, bucketed per minute.

| Column Name  | Data Type         | Description                                                         |
| ------------ | ----------------- | ------------------------------------------------------------------- |
| timestamp    | TIMESTAMP         | Timestamp of the price data                                         |
| high         | FLOAT             | Highest price during the timestamp period                           |
| low          | FLOAT             | Lowest price during the timestamp period                            |
| open         | FLOAT             | Opening price at the start of the timestamp period                  |
| close        | FLOAT             | Closing price at the end of the timestamp period                    |
| pair         | CHARACTER VARYING | Asset trading pair                                                  |