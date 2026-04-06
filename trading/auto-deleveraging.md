# Auto-Deleveraging

ADL is the last-resort rebalancing mechanism used when liquidation and insurance are insufficient.

## When ADL activates

- liquidation cannot be completed at safe prices
- insurance fund is insufficient for the resulting deficit

## Queue ranking

Accounts are ranked by a score derived from leverage and profitability. High-leverage, high-profit positions are typically most exposed to ADL.

## Outcome

ADL reduces offsetting positions without relying on the live order book. It is designed to restore solvency quickly at the cost of interrupting otherwise profitable positions.
