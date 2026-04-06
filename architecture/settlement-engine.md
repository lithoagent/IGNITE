# Settlement Engine

The settlement engine transforms executed trades into batched on-chain updates.

## Why batch settlement

Submitting every fill individually to a settlement contract is expensive and unnecessary. Ignite instead aggregates trade outputs into deterministic state deltas and commits them in batches.

## State delta

```ts
type StateDelta = {
  account: string
  balanceChanges: Record<string, string>
  positionChanges: Record<string, {
    sizeDelta: string
    marginDelta: string
    realizedPnlDelta: string
  }>
}
```

## Batch model

```ts
type Batch = {
  id: string
  deltas: StateDelta[]
  merkleRoot: string
  createdAt: number
}
```

## Commit flow

1. Executions produce balance and position deltas  
2. Deltas are normalized and aggregated  
3. A batch root is computed  
4. The root and batch id are submitted on-chain  
5. Indexers and verifiers track confirmation and finality  

## Future proof paths

The batching model is compatible with:

- zk-proved state transitions
- fraud-proof challenge windows
- external verifiers and mirrors
