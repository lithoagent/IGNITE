# Matching Engine

The Ignite matching engine implements a central limit order book with deterministic price-time priority.

## Core structures

```ts
type Order = {
  id: string
  user: string
  side: "buy" | "sell"
  type: "limit" | "market" | "ioc" | "fok" | "post_only"
  price: bigint
  size: bigint
  remaining: bigint
  timestamp: bigint
}
```

```ts
type PriceLevel = {
  price: bigint
  queue: Order[]
}
```

```ts
type OrderBook = {
  bids: PriceLevel[]
  asks: PriceLevel[]
}
```

## Matching rules

### Price priority
Best available price always matches first.

### Time priority
Within a price level, earlier resting orders match before later orders.

### Order type behavior

- **Limit:** match immediately where possible, rest remaining size if allowed
- **Market:** consume available opposite-side liquidity until size completes or the order is exhausted
- **IOC:** fill immediately and cancel any unfilled remainder
- **FOK:** only execute if the entire requested size can be matched instantly
- **Post-only:** reject if any part would cross the spread on entry

## Matching pseudocode

```ts
function match(order, book) {
  while (order.remaining > 0n) {
    const best = bestOpposite(order, book)
    if (!best) break
    if (!crosses(order, best.price)) break

    while (best.queue.length > 0 && order.remaining > 0n) {
      const resting = best.queue[0]
      const fill = min(order.remaining, resting.remaining)
      executeTrade(order, resting, fill, best.price)
      order.remaining -= fill
      resting.remaining -= fill
      if (resting.remaining === 0n) best.queue.shift()
    }

    if (best.queue.length === 0) removePriceLevel(best)
  }

  if (order.remaining > 0n && canRest(order)) {
    addToBook(order)
  }
}
```

## Persistence model

The matching engine keeps the canonical working book in memory and writes event records to a durable log. Recovery replays the log into a clean state snapshot.
