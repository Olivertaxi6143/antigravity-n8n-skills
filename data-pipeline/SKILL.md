---
activation: model_decision
name: data-pipeline
description: "ETL, transforms, Airflow, dbt, streaming. Se activa con pipelines de datos, ETL, data engineering."
---
# Data Pipeline Design

## Principios
- Pipelines idempotentes (re-run safe)
- Schema validation on ingest
- Monitor data drift
- Incremental processing when possible

## Reproducibilidad
- Pin dataset versions (DVC, S3 versioning)
- Deterministic seeds
- Lock dependencies
- Document: source, transform, params

## Evaluation
- Métricas offline + regression tests
- Golden datasets para integration tests
- Track metrics over time