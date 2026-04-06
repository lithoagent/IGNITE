# Strategies

Ignite strategies can range from deterministic rule sets to probabilistic ML-based decision systems.

## Common strategy classes

- momentum
- mean reversion
- market making
- cross-chain arbitrage
- liquidation execution
- portfolio rebalancing

## Pipeline

```text
Market Data -> Signal Extraction -> Decision -> Execution -> Feedback -> Parameter Update
```

## Best practices

- separate alpha generation from execution
- keep risk checks out-of-band and in-band
- log all decisions for auditability
