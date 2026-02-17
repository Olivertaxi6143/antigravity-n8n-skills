---
activation: model_decision
name: db-architect
description: "Diseño de schemas, migraciones, optimización de queries. Se activa con schemas, migrations, queries."
---
# Database Architecture

## Schema Design
- PK: UUID v7 (sortable) o auto-increment (interno)
- Timestamps: `created_at`, `updated_at` UTC en toda tabla
- Indexes: FKs, columnas WHERE/ORDER BY frecuentes
- Constraints: NOT NULL por defecto, FK con ON DELETE strategy

## Migrations
- Forward (up) + Rollback (down) MANDATORY
- Additive primero, destructive después
- Test: up + down + up → consistent

## Queries
- EXPLAIN antes de optimizar
- No N+1: batch/join/eager loading
- No SELECT *. Pagination always.
- Connection pooling. Transacciones cortas.