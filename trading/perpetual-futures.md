# Perpetual Futures

Perpetual futures are the core derivatives product of Ignite.

## Product characteristics

- no expiry date
- leverage up to the configured market cap
- cross and isolated margin support
- periodic funding payments between longs and shorts

## Position accounting

Each perp position tracks:

- signed size
- average entry price
- margin allocation
- realized PnL
- unrealized PnL from mark price

## Core formulas

```text
Unrealized PnL (long) = size * (mark - entry)
Unrealized PnL (short) = size * (entry - mark)
```

## Risk interaction

Perp positions are continuously checked by the risk engine. Mark price, not last trade price, controls liquidation eligibility.
