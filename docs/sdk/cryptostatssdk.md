---
sidebar_position: 1
---

# CryptoStats SDK Object

## Constructor

```
new CryptoStatsSDK(options: CryptoStatsOptions)_

CryptoStatsOptions {
  ipfsGateway?: string;
  cache?: ICache;
  infuraKey?: string;
  moralisKey?: string;
  mongoConnectionString?: string;
  redisConnectionString?: string;
  executionTimeout?: number;
  adapterListSubgraph?: string;
  onLog?: (level: LOG_LEVEL, ...args: any[]) => void;
}
```

### ipfsGateway

the 

### cache

<!-- // TODO -->

A caching provider (see Caching section).

By default, a simple MemoryCache object will be used.

### infuraKey

Infura API key, to allow access to blockchain data queries.

### moralisKey

Moralis API key, to allow access to blockchain data queries.

Note: Moralis may be preferred to Infura, due to generous free archive node queries.

### mongoConnectionString

### redisConnectionString

### executionTimeout

### adapterListSubgraph

### onLog

A callback function to receive log messages emitted by adapters.
