# Oracles

Perpetual markets require robust reference prices for margin, liquidation, and funding.

## Sources

Ignite is designed to consume:

- Chainlink
- Pyth
- internal time-weighted average prices
- exchange-derived basis components

## Price hierarchy

### Index price
The fair external market reference derived from trusted sources.

### Mark price
The risk price used to compute margin and liquidation thresholds. Mark price is typically the index price plus a bounded basis adjustment.

## Failure handling

If an oracle source fails or deviates beyond configured tolerances:

- switch to fallback source
- use TWAP smoothing
- reduce leverage caps
- trigger circuit breakers if needed
