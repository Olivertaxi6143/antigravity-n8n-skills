---
activation: model_decision
name: api-design
description: "Diseño de endpoints REST/GraphQL, contratos, versionamiento. Se activa al diseñar o modificar APIs."
---
# API Design

## REST Conventions
- Resources as nouns: `/api/v1/users`, `/api/v1/orders`
- HTTP methods: GET(read), POST(create), PUT(full update), PATCH(partial), DELETE
- Status codes estándar: 200, 201, 204, 400, 401, 403, 404, 409, 422, 429, 500
- Pagination: cursor-based preferred
- Error shape: `{ error: { code, message, details? } }`

## Contratos
- Schema validation at edges (Zod/Joi/Pydantic)
- Versioning: URL prefix `/v1/`
- OpenAPI spec sincronizado con código