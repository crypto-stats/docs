# Graph

The HTTP library allows simple HTTP requests to be sent in an adapter.

## `sdk.graph.query(subgraph: string, query: string, variables?: any): Promise<any>`

Query a subgraph hosted by The Graph's hosted service.

### Example

```ts
const graphQuery = `query fees($date: Int!) {
  uniswapDayDatas(where: {date: $date}) {
    feesUSD
  }
}`;

const data = await sdk.graph.query('ianlapham/uniswap-v3-prod', graphQuery, {
  date: sdk.date.dateToTimestamp(date),
});
```

## `sdk.graph.query(options: QueryOptions): Promise<any>`

```ts
interface QueryOptions {
  subgraph: string;
  query: string;
  variables?: any;
  operationName?: string;
  node?: string;
}
```

This overridden version of the `query()` function allows passing

### Example

```ts
const query = `query fees($date: Int!) {
  pancakeDayDatas(where: { date: $date }) {
    dailyVolumeUSD
  }
}`;

const data = await sdk.graph.query({
  subgraph: 'pancakeswap/exchange-v2',
  query,
  node: 'https://bsc.streamingfast.io',
  variables: {
    date: sdk.date.dateToTimestamp(date),
  },
});
```
