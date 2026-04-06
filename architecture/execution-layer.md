# Execution Layer

The execution layer is responsible for receiving orders, validating them, sequencing them, and matching them against the order book.

## Goals

- Sub-millisecond matching within a market partition
- Deterministic price-time priority
- Clear separation between acceptance, matching, and settlement
- Efficient broadcasting to downstream systems

## Flow

1. A client signs an order or API action
2. The gateway verifies the request and normalizes fields
3. The request is routed to the market partition
4. The matching engine validates executable constraints
5. Matches produce fills and state deltas
6. Updates are sent to the risk engine and settlement pipeline

## Market partitioning

Ignite runs one matching thread or deterministic execution lane per market to avoid race conditions inside a book. Horizontal scaling comes from running many markets in parallel rather than sharing one book across concurrent workers.

## Determinism constraints

- fixed-point integer math
- canonical field ordering
- monotonic market sequence numbers
- no price-time ambiguity inside a price level
