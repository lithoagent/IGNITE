# Binary Protocol

Ignite supports a compact binary protocol for low-latency clients.

## Why binary

- lower serialization overhead than JSON
- smaller payloads
- faster parsing on both ends
- improved efficiency for colocated or institutional strategies

## Example frame layout

| Field | Size |
|---|---:|
| opcode | 1 byte |
| order id | 8 bytes |
| price | 8 bytes |
| size | 8 bytes |
| side | 1 byte |
| timestamp | 8 bytes |

## Opcodes

| Opcode | Meaning |
|---|---|
| `0x01` | place order |
| `0x02` | cancel order |
| `0x03` | modify order |

## Determinism requirement

Binary transport changes how messages are encoded, not how orders are interpreted. The canonical engine state transition rules remain identical across REST, WebSocket command channels, and binary transport.
