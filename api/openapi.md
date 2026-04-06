# OpenAPI

A full OpenAPI specification can be generated from the route set documented in this package. A starter path model is included below.

```yaml
openapi: 3.1.0
info:
  title: Ignite DEX API
  version: 1.0.0
servers:
  - url: https://api.ignite.ac
paths:
  /markets:
    get:
      summary: List markets
  /orderbook/{pair}:
    get:
      summary: Get order book snapshot
  /orders:
    post:
      summary: Place order
  /positions:
    get:
      summary: Get account positions
```
