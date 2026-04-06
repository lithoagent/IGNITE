# Rate Limits

Rate limiting protects engine stability and preserves fairness.

## Example tiers

| Tier | Typical limit |
|---|---:|
| Public | 50 req/s |
| Authenticated | 200 req/s |
| Institutional | custom |

## Enforcement patterns

- token bucket for bursts
- per-IP and per-account checks
- route-specific caps
- backpressure and queue protection

## WebSocket notes

Excessive subscriptions, authentication failures, or malformed messages may trigger connection-level throttling or disconnects.
