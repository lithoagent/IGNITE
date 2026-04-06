# REST API

## Markets

### `GET /markets`

Returns market metadata, status, precision parameters, leverage caps, and risk tier schedules.

## Order Book

### `GET /orderbook/:pair`

Returns a snapshot of bids and asks for the specified pair.

## Place Order

### `POST /orders`

```json
{
  "pair": "ETH/USDT",
  "side": "buy",
  "type": "limit",
  "price": 2000,
  "size": 1,
  "timestamp": 1710000000,
  "signature": "0x..."
}
```

## Cancel Order

### `DELETE /orders/:id`

Cancels an open order by id.

## Positions

### `GET /positions`

Returns open positions, margin state, entry price, mark price, and PnL.

## Funding

### `GET /funding-rate/:pair`

Returns current and historical funding information.

## Margin Update

### `POST /margin/update`

Adjusts isolated margin allocation or collateral configuration where supported.
