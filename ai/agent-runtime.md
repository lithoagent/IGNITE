# Agent Runtime

An agent runtime encapsulates strategy logic, permissions, state, and risk configuration.

## Example model

```ts
type Agent = {
  id: string
  owner: string
  strategyId: string
  riskProfileId: string
  status: "active" | "halted" | "sandboxed"
}
```

## Capabilities

- subscribe to market data
- issue orders
- manage positions
- consume strategy signals
- pause on guardrail breach
