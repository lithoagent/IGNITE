# Vault Contract

The vault contract is the on-chain custody layer for user balances and locked margin.

## Responsibilities

- accept deposits
- process withdrawals
- track available balances
- track locked margin
- expose authorized hooks for engine-mediated collateral locking

## Interface sketch

```solidity
interface IVault {
    function deposit(address token, uint256 amount) external;
    function withdraw(address token, uint256 amount) external;
    function lockMargin(address user, uint256 amount) external;
    function unlockMargin(address user, uint256 amount) external;
}
```

## Security notes

- deposits require token transfer success
- withdrawals respect free collateral checks
- margin locking is restricted to authorized engine roles
