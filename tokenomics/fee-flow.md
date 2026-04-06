# Fee Flow

IGNT sits at the center of protocol fee routing.

## Flow

1. a user executes a trade
2. the fee is paid in IGNT
3. the fee router receives the amount
4. the router splits the amount into treasury, stakers, incentives, and burn

## Example target split

| Destination | Share |
|---|---:|
| Treasury | 40% |
| Stakers | 30% |
| Liquidity incentives | 20% |
| Burn | 10% |

## Deflationary behavior

Burning a portion of fee flow reduces circulating supply over time as protocol usage increases.
