# Risk Engine

The risk engine enforces solvency constraints before and after execution.

## Responsibilities

- validate available margin before order acceptance
- update account equity after fills
- compute liquidation eligibility
- trigger partial liquidation and full liquidation logic
- rank accounts for ADL when necessary

## Equity model

```text
Equity = Wallet Balance + Unrealized PnL
Notional = abs(Position Size * Mark Price)
Margin Ratio = Equity / Notional
```

## Margin thresholds

| Condition | Meaning |
|---|---|
| MR > IM | position is comfortably margined |
| MM < MR <= IM | account is above liquidation threshold but constrained |
| MR <= MM | account is liquidatable |

## Dynamic risk tiers

Large notional positions require higher initial and maintenance margin to control tail risk. Tiers are evaluated per market and can also roll into account-level concentration checks.

## Cross and isolated support

In cross margin mode, account equity is shared across positions. In isolated mode, a specific allocation of collateral backs a specific position or product bucket.

## Liquidation trigger

A liquidation event is emitted when the account falls below maintenance margin at the current mark price and no immediately available collateral adjustment restores solvency.
