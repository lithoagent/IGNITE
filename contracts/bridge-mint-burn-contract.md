# Bridge Mint/Burn Contract

The bridge contract family handles canonical token mobility across supported networks.

## Model

- lock or burn on source chain
- relay authenticated message
- mint or release on destination chain

## Required protections

- replay protection using message hashes or nonces
- role-based mint and burn authority
- emergency pause controls
