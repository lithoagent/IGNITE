# Fee Router

The fee router is the economic distribution hub of Ignite.

## Responsibilities (updated)

- collect trading fees
- route treasury share
- route staking rewards
- route incentive allocation
- burn configured fee share

## Example fee split

| Destination | Target share |
|---|---:|
| Treasury | 40% |
| Stakers | 30% |
| Liquidity incentives | 20% |
| Burn | 10% |

## Operational notes

Local chain fee routers can settle chain-local fee flow while syncing with broader protocol accounting.
