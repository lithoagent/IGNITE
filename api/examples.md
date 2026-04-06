# Examples

## Subscribe to order book

```ts
const ws = new WebSocket("wss://ws.ignite.ac");
ws.onopen = () => {
  ws.send(JSON.stringify({
    op: "subscribe",
    channel: "orderbook",
    pair: "ETH/USDT"
  }));
};
```

## Signed order sketch

```ts
const order = {
  pair: "ETH/USDT",
  side: "buy",
  type: "limit",
  price: "2000000000",
  size: "1000000",
  nonce: 42,
  timestamp: Date.now()
};

// hash and sign using EIP-712 domain config
```

## REST fetch

```ts
const res = await fetch("https://api.ignite.ac/markets");
const markets = await res.json();
```
