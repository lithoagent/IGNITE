# Contracts Overview

Ignite uses modular contracts for custody, settlement, fee routing, staking, incentives, bridging, and governance.

## Core contracts

- `IgniteToken.sol`
- `Vault.sol`
- `PerpsClearing.sol`
- `FeeRouter.sol`
- `Staking.sol`
- `Incentives.sol`
- `BridgeMintBurn.sol`
- `Governance.sol`

## Design goals

- explicit access control
- upgradeability where appropriate
- isolated responsibilities
- multi-chain deployment compatibility
