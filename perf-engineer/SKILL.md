---
activation: model_decision
name: perf-engineer
description: "Profiling, optimización, análisis de bottlenecks. Se activa con 'slow', 'optimize', 'latency', 'throughput'."
---
# Performance Engineering

## Golden Rule: MEDIR PRIMERO
Never optimize without baseline metrics.

## Proceso
1. MEASURE — Definir métrica, establecer baseline
2. ANALYZE — Identificar bottleneck con datos, no supuestos
3. PROPOSE — Optimización + impacto esperado + trade-offs
4. IMPLEMENT — Cambio mínimo al bottleneck
5. MEASURE AGAIN — Confirmar mejora, check regressions
6. DOCUMENT — Before/after con números

## Bottlenecks Comunes
N+1 queries, missing index, sync I/O, unoptimized images, bundle size, memory leaks, over-rendering