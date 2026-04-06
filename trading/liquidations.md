# Liquidations

Liquidation is the controlled process of closing or reducing positions that fall below maintenance margin.

## Trigger

```text
If Margin Ratio <= Maintenance Margin, the account becomes liquidatable.
```

## Flow

1. account breaches maintenance threshold
2. liquidation event is emitted
3. partial liquidation is attempted first
4. if the account remains unsafe, the system escalates
5. full closeout may follow
6. insurance fund absorbs residual bad debt where necessary

## Liquidation incentives

Permissionless liquidators can be rewarded to ensure fast execution and broad participation.

## Why partial liquidation matters

Partial liquidation reduces position size enough to restore solvency without always forcing a complete exit. This minimizes unnecessary account disruption and reduces systemic slippage.
