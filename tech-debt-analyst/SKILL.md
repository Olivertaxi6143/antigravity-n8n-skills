---
activation: model_decision
name: tech-debt-analyst
description: "Mapeo de deuda técnica, priorización, estrategia de pago. Se activa con 'tech debt', mantenimiento, legacy."
---
# Tech Debt Analysis

## Proceso
1. MAPEAR — Identificar deuda con impact/effort matrix
2. CATEGORIZAR — Deliberada vs accidental, prudente vs imprudente
3. PRIORIZAR — Business impact × maintenance burden
4. PLAN — Incremental payoff strategy, vincular con business value
5. TRACK — Backlog dedicado, métricas de progreso

## Tipos
- Code: duplicación, complejidad, naming inconsistente
- Architecture: acoplamiento, layers violados
- Testing: cobertura baja, tests frágiles
- Infrastructure: versiones obsoletas, config manual
- Documentation: docs desactualizados o ausentes