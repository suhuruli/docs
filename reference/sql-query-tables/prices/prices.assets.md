---
description: SQL table schema for prices.assets
---

# prices.assets

All assets verified and useable within SpiceAI.

| Column Name      | Data Type         | Description                                                |
| ---------------- | ----------------- | ---------------------------------------------------------- |
| asset\_id        | CHARACTER VARYING | Unique identifier for the asset across SpiceAI platform    |
| name             | CHARACTER VARYING | Display name of the underlying asset/token                 |
| eth\_address     | CHARACTER VARYING | Ethereum address associated with the asset, otherwise NULL |
| polygon\_address | CHARACTER VARYING | Polygon address associated with the asset, otherwise NULL  |
