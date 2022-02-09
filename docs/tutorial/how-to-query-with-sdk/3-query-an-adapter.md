---
sidbar_position: 3
---

# Query an adapter

Adapters are stored in collections. There are multiple ways to access an adapter to make queries with.

### Using a collection
You can fetch an adapter from a collection to make queries by ... 

```
async function queryAdapter() {
    const collection = sdk.getCollection('fees')
    await collection.fetchAdapters()
    const adapter =  collection.getAdapter('sushiswap-ethereum')

    const oneDayTotalFees = await adapter.executeQuery('oneDayTotalFees', length='2022-06-05')

    ...
}
```

You can also query a collection directly to get a list of results of each adapter

```
const results = await collection.executeQuery('oneDayTotalFees')
```

### Using IFPS CID
You can also fetch an adapter directly to make queries via IFPS using the CID as an argument
```
async function queryAdapter() {
    const adapter = await fetchAdapterByIFPS(cid='xxx')
    const oneDayTotalFees = await adapter.executeQuery('oneDayTotalFees', length='2022-06-05')

    ...
}
```

> 
> 
> ## 💡 Tip
> You can execute multiple queries on an adapter or a collection using the `executeQueries()` method.