# Perps Clearing Contract

The perps clearing contract applies settled trade outputs to account state.

## Responsibilities

- update balance deltas
- update position state
- account for realized PnL
- apply fees
- emit settlement events

## Position model

```solidity
struct Position {
    int256 size;
    uint256 entryPrice;
    uint256 margin;
}
```

## Settlement hook

```solidity
function settleTrade(address trader, int256 pnl, uint256 fee) external;
```
