# Authentication

Ignite uses signature-based authorization.

## Supported models

- EIP-712 typed data signatures
- session keys for low-latency delegated trading
- API keys for institutional and bot workflows

## Signing goals

- authenticate the account owner
- prevent replay through nonces and timestamps
- allow secure delegated action where supported

## Canonical signed order fields

```json
{
  "user": "0x...",
  "pair": "ETH/USDT",
  "side": "buy",
  "type": "limit",
  "price": "2000000000",
  "size": "1000000",
  "nonce": 42,
  "timestamp": 1710000000
}
```
