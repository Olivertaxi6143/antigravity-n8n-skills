---
activation: model_decision
name: estimator
description: "Sizing de esfuerzo, análisis de complejidad, riesgos. Se activa con 'cuánto toma', 'complejidad', 'estimar'."
---
# Effort Estimation

## T-Shirt Sizing
- XS: < 2 horas. Un archivo, patrón conocido.
- S: 2-8 horas. Pocos archivos, scope claro, tests existentes.
- M: 1-3 días. Múltiples archivos, patrones nuevos.
- L: 3-5 días. Cambio de arquitectura, migraciones.
- XL: 1-2 semanas. Sistema nuevo, refactor mayor.

## Reglas
- Nunca single-point estimates. Siempre rango o T-shirt.
- Desglosar en tareas. Estimar cada una.
- Identificar unknowns explícitamente.
- Incluir: coding, testing, review, deploy, docs.
- Buffer 20-50% para unknowns e integración.