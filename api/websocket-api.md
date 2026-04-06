# WebSocket API

The WebSocket API is the primary interface for real-time trading clients.

## Connection

```text
wss://ws.ignite.ac
```

## Public channels

- `orderbook`
- `trades`
- `ticker`
- `funding`

## Private channels

- `orders`
- `fills`
- `positions`
- `balances`

## Subscribe example

```json
{
  "op": "subscribe",
  "channel": "orderbook",
  "pair": "ETH/USDT"
}
```

## Order book delta example

```json
{
  "type": "delta",
  "pair": "ETH/USDT",
  "sequence": 10452,
  "bids": [[2000, 5]],
  "asks": [[2001, 3]]
}
```

## Private auth example

```json
{
  "op": "auth",
  "key": "api_key",
  "sig": "0x..."
}
```
