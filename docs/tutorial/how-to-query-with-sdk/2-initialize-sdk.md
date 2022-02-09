---
sidebar_position: 2
---

# Initialize CryptoStats SDK

Before you can start using the sdk, you need to import it and initialize it with a setup based on the data we want to query. 

```
const { CryptoStatsSDK } = require('cryptostats/sdk')

const sdk = new CryptoStatsSDK()
```



> ## 💡 Tip
If you will be making on-chain queries, it is recommeneded that you add the needed configurations when initializing the SDK. 

Example if you want to make queries that require archive nodes. You can initialize the sdk with a [Moralis](https://moralis.io/) API key.

```
const sdk = CryptoStatsSDK({
    moralisKey: 'xxxx',
    })
```

You can find more information about SDK configuration [here](/sdk/cryptostatssdk)