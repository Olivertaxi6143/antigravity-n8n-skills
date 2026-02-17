---
activation: model_decision
name: migrate
description: "Planifica migraciones y upgrades. Se activa con 'upgrade', 'migrate', cambios de versión."
---
# Migration Planner

## Proceso
1. Análisis de breaking changes (CHANGELOG)
2. Plan paso a paso con rollback strategy
3. Compatibilidad de dependencias
4. Test migration path: up + down + up
5. Documentar cambios requeridos en código
6. Deploy plan con pre/post steps