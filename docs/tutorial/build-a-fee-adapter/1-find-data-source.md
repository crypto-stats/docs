---
sidebar_position: 1
---

# 1. Find a data source for fees

Before we can add a new protocol to CryptoStats, we first need to understand the fee model of the protocol
and find a reliable data source

## Understand the protocol's fee model

First, we need to understand the fee model of the protocol. For any protocol, we need to ask the questions:

* Who pays for fees?
* Where do the fees go?
* What determines the amount of fee paid?
* What assets are fees paid in?

Understanding these, we should be able to come up with a simple math formula for deriving the fees in US dollars.

For example, we know that Ethereum fees are paid by users, and are partially burned, partially paid to miners. Fees
are always paid in ETH, and the amount is determined by blockspace demand (the gas price) multiplied by the
transaction complexity.

Therefore, the USD fee from any Ethereum transaction is simply _gas fee * ETH price_.

Uniswap is slightly more complicated, since the 0.3% fee is paid from any asset being swapped. Therefore, the USD fee
from any Uniswap trade is _assetIn amount * assetIn price * 0.003_.

### Supply-side fees vs. protocol fees

It's important to distinguish between _supply-side fees_ and _protocol fees_.

Supply-side fees are paid to users that contribute resources to a protocol, such as miners & validators for L1s,
liquidity providers on exchanges and lenders on lending protocols.

Protocol-fees represent value that is accrued to a protocol's treasury, or to tokenholders themselves (such as
through dividends or token buy-backs).

For example, SushiSwap distributes 0.25% of each trade to liquidity providers, and collects 0.05% of each trade
towards the Sushi treasury.

When we build our adapter, we'll want to provide queries for _both_ of these values.

## Check if the protocol fits the listing criteria

Anyone is welcome to build adapters for any protocol that they chose. However, in order to be listed
on the CryptoStats "fee" collection, a protocol must meet the listing criteria.

Current listing criteria [can be found on the CryptoStats forum](https://forum.cryptostats.community/t/fee-revenue-listing-criteria/96)..

## Find a data source

CryptoStats aims to pull data from sources that are trustworthy and reliable.

1. On-chain data
2. Open-source, public indexers (such as The Graph subgraphs)
3. Trustworthy, open-source APIs provided by the team behind a protocol
4. Data provided by trustworthy, independent third-parties (CoinMetrics)
5. Closed-source data providers

Using less-trustworthy the data sources increases the likelyhood that an adapter will be rejected
for inclusion in a collection.

Data must also be freely available to all (meaning premium data sources such as Dune Analytics can not be used).

### If necessary: build a subgraph

Many DeFi protocols on EVM-based chains already have subgraphs deployed to The Graph which index fees.
You can find existing subgraphs by searching on The Graph's [hosted service page](https://thegraph.com/hosted-service/)
(queries to the decentralized Graph protocol are not supported at this time).

If there is no subgraph available, building a new one may be the easiest way to index fees.

## Next step: build your adapter

Once you have found all necessary data-sources, it's time to combine them in a new data adapter!

[2. Write the CryptoStats adapter](./2-write-adapter)
