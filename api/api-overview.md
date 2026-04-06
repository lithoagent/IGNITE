# API Overview

Ignite exposes three primary integration surfaces:

- REST API for control-plane actions and queries
- WebSocket API for real-time market and account streams
- binary protocol for ultra-low latency workflows

## Interface split

REST is ideal for account queries, snapshots, and order management. WebSocket is the default for live market data and user updates. Binary transport is intended for HFT-style clients that want lower serialization overhead.

## Base endpoints

- REST: `https://api.ignite.ac`
- WebSocket: `wss://ws.ignite.ac`
