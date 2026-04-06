# Funding Rates

Funding keeps perpetual contract prices anchored to spot.

## Intuition

When perpetuals trade rich relative to index, longs pay shorts. When perpetuals trade cheap, shorts pay longs.

## Simplified model

```text
Funding Rate = (Mark Price - Index Price) / Index Price
Funding Payment = Position Notional * Funding Rate
```

## Operational model

- funding is computed periodically
- payment is applied as a balance adjustment
- funding does not require order book interaction
- historical funding values are indexed and queryable

## Design considerations

- cap extreme funding values
- smooth noisy basis data
- make rate publication predictable for market makers
