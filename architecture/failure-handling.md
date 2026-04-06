# Failure Handling & Recovery

Ignite is built to degrade safely.

## Failure classes

- matching node crash
- state desynchronization
- oracle deviation
- settlement chain outage
- networking partition
- streaming backlog

## Recovery model

### Snapshot + replay

1. load latest durable snapshot
2. replay event log from snapshot point
3. compare derived state with indexed records
4. resume from canonical state

### Circuit breakers

Ignite can pause markets or settlement routes when:

- oracle deviation breaches threshold
- batch confirmation lags beyond tolerance
- system risk indicators cross configured levels

### Emergency mode

Emergency mode prioritizes fund safety and controlled recovery:

- new trading may pause
- withdrawals may remain enabled where risk allows
- governance or guardian controls can intervene
