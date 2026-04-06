# Supported Networks

Ignite DEX is designed for deployment and execution across four primary environments.

## Lithosphere

- **Environment:** Makalu
- **Chain ID:** 700777
- **Role:** Core ecosystem, identity integration, AI coordination, native LEP100 deployment

## Base

- **Role:** Primary ERC-20 liquidity hub
- **Primary use cases:** trading fees, staking, liquidity routing

## Arbitrum

- **Role:** Perpetual trading expansion and margin-intensive activity
- **Primary use cases:** perps collateral, high-frequency execution surfaces

## BNB Chain

- **Role:** Retail access and incentive-heavy environments
- **Primary use cases:** fee token deployment, broad user distribution, liquidity programs

## Chain abstraction model

Ignite exposes a single product surface with chain-aware settlement underneath. In practice this means:

- deposits are chain-specific
- vault balances are chain-tracked
- risk can be computed at a global account level
- settlement is ultimately final on the underlying chain

## Token standard map

| Network | Standard | IGNT Form |
|---|---|---|
| Lithosphere | LEP100 | Native ecosystem form |
| Base | ERC-20 | Liquidity and fee asset |
| Arbitrum | ERC-20 | Trading and collateral asset |
| BNB Chain | ERC-20 | Fee and rewards asset |
