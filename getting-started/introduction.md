# Introduction

Ignite DEX is a next-generation decentralized exchange built to deliver professional trading infrastructure without giving up self-custody.

The protocol is designed around five goals:

1. **Execution performance** comparable to modern centralized venues  
2. **On-chain settlement** with user-owned collateral  
3. **Multi-chain reach** across Lithosphere, Base, Arbitrum, and BNB Chain  
4. **Permissionless market creation** and open liquidity participation  
5. **AI-native infrastructure** for autonomous strategies and intelligent execution  

Ignite supports spot markets today in the architecture model and is designed around perpetual futures as a core product. Options, launch infrastructure, advanced analytics, and agent-driven services fit into the same system.

## Who this documentation is for

This documentation is intended for:

- Traders using the Ignite terminal
- Market makers integrating at low latency
- Developers building bots, SDK integrations, and dashboards
- Protocol engineers reviewing core architecture
- Partners evaluating the IGNT token economy

## Product pillars

### Hybrid execution model

Ignite separates execution from settlement. Orders are matched by a deterministic off-chain engine and then committed on-chain in batched state transitions.

### Non-custodial security

Collateral is held in protocol vaults controlled by smart contracts. Users retain wallet ownership and interact via signature-based authorization.

### Multi-chain liquidity and margin

Ignite supports execution and settlement across multiple chains while exposing a unified product surface to the user.

### AI-native system design

Autonomous agents are a first-class concept in Ignite, enabling sophisticated execution, market making, and analytical workflows.
