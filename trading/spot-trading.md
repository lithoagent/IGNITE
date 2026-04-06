# Spot Trading

Spot markets on Ignite are built around transparent price-time matching and multi-source liquidity support.

## Features

- limit and market orders
- post-only protection
- immediate-or-cancel and fill-or-kill execution
- deep aggregated liquidity sources where supported

## Settlement

Spot trades update token balances directly inside the relevant vault model. Balance deltas are committed through the settlement engine.

## Notes for integrators

- prices and sizes should be encoded using market-specific precision
- partial fills are expected
- resting orders remain live until matched, cancelled, or expired
