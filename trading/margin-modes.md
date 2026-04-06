# Margin Modes

Ignite supports both cross and isolated margin.

## Cross margin

Cross margin uses all available account equity to support open positions.

### Benefits
- greater capital efficiency
- lower chance of isolated liquidation on a single position

### Tradeoffs
- losses in one market can affect the whole account

## Isolated margin

Isolated margin allocates a specific collateral amount to a specific position.

### Benefits
- contained downside on a position
- easier strategy compartmentalization

### Tradeoffs
- less capital efficiency

## Shared margin abstraction

In the multi-chain model, Ignite can expose a unified portfolio view while still tracking where collateral lives and how it is reserved.
