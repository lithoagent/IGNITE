# Data & Indexing

Ignite separates execution-critical state from analytical state.

## Execution-critical state

- live order books
- current balances
- position state
- margin and liquidation status

This state sits in memory and durable event logs.

## Indexed state

A separate data pipeline writes query-friendly records into analytical databases such as Postgres and ClickHouse for:

- historical trades
- candlesticks
- positions history
- funding history
- referral and incentive analytics

## Streaming

A message bus and WebSocket system distribute low-latency market data for:

- order book deltas
- trades
- positions
- account updates
- funding events

## Design rule

User interfaces and dashboards read from the indexed layer where possible. The engine only answers latency-critical and authoritative requests.
