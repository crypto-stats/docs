# Chain Data

Fetch metadata about various blockchains.

## `getBlockNumber(date: string | number | Date, chain: string = 'ethereum'): Promise<any>`

Fetch the block number of an EVM chain on a given date.

Supports the date inputted as a standard date string (ex 2021-01-01), a Unix timestamp, or
a Javascript `Date` object.

### Supported chains

* ethereum
* fantom
* bsc
* polygon
* avalanche
* arbitrum-one
* optimism
* xdai
* kovan
* goerli
* rinkeby

### Example

```ts
const date = '2022-01-01';
const block = await sdk.chainData.getBlockNumber(date, 'polygon');
```
