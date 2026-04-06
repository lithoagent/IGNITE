# Cross-Chain Architecture

Ignite is multi-chain by design. The core challenge is to maintain clear chain-local settlement while exposing a unified user experience.

## Principles

- Settlement remains explicit on the destination chain
- Messages between chains are replay-protected
- Global account views are computed from chain-specific balances and positions
- Risk is chain-aware even when user UX is unified

## Logical model

```text
Global Account
  |- Lithosphere balances
  |- Base balances
  |- Arbitrum balances
  |- BNB balances
  \- Aggregated PnL and margin state
```

## Bridge and messaging

Ignite uses a canonical mint/burn bridge model for asset mobility between supported environments.

### Transfer flow

1. Asset is locked or burned on source chain
2. A bridge message is emitted with nonce and source metadata
3. Relayers observe and relay the message
4. Destination chain contract validates message uniqueness
5. Asset is minted or unlocked on destination chain

## Risks and controls

- relayer trust assumptions are explicit
- message hashes are tracked to prevent replay
- chain outages can pause specific routes without halting the entire exchange
