# Coordination Protocol

Agents may coordinate through a message bus.

## Use cases

- multi-agent hedging
- liquidity syndication
- arbitrage execution across venues or chains
- shared capital allocation

## Message model

```ts
type AgentMessage = {
  from: string
  to: string
  type: string
  payload: unknown
}
```

## Safety

Coordination should be rate-limited, permission-aware, and observable. No coordination path should bypass account-level risk enforcement.
