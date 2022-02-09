---
sidebar_position: 1
---

# How to make queries with REST API
The REST API is the most convenient way to access data from CryptoStats adapters. 

### How to make a single query
To make a single query on a collection. Send a GET request to 
```
https://api.cryptostats.community/api/v1/<collection-id>/<query>/<arg>
```

For example, to get the daily total fees for listed protocols in the fees collection;

```
const url = 'https://api.cryptostats.community/api/v1/fees/oneDayTotalFees/2022-01-01';
const response = await fetch(url);
const json = await response.json();
console.log(json);
```

### How to make multiple queries

To make multiple queries on a collection, send a GET request to

```
https://api.cryptostats.community/api/v1/<collection-id>/<query-1>,<query-2>/<query-1-arg>,<query-2-arg>
```

For example, to get the current treasury balance in USD and the current liquid treasury balance in USD

```
const url = 'https://api.cryptostats.community/api/v1/treasuries/currentTreasuryUSD,currentLiquidTreasuryUSD';
const response = await fetch(url);
const json = await response.json();
console.log(json);
```

### Accessing adapter meta data  

> ## 💡 Tip
> You can access metadata for adapters by using the  `metadata=True` query parameter
> ```
> https://api.cryptostats.community/api/v1/<collection-id>/<query>/<arg>?metadata=True
> ```
> 