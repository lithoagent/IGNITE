# TypeScript SDK

Ignite provides a TypeScript SDK for application and bot integrations.

## Install

```bash
npm install @ignite/dex-sdk
```

## Initialize client

```ts
import { IgniteClient } from "@ignite/dex-sdk";

const client = new IgniteClient({
  chains: ["litho", "base", "arbitrum", "bnb"],
  rpc: "https://rpc.litho.ai",
  chainId: 700777
});
```

## Connect wallet

```ts
await client.wallet.connect();
```

## Place order

```ts
await client.trade.placeOrder({
  pair: "ETH/USDT",
  side: "buy",
  type: "limit",
  price: 2000,
  size: 1
});
```

## Fetch markets

```ts
const markets = await client.market.getAll();
```
