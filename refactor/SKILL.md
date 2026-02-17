---
name: refactor
description: "Mejora incremental preservando comportamiento. Se activa con 'refactor', 'clean up', code smells."
activation: always_on
---
# Code Refactoring

## Reglas
- Tests VERDES antes de refactorizar
- Un tipo de refactoring por commit
- Verificar tests después de cada paso
- NUNCA mezclar refactor con features

## Tipos Comunes
- Extract function (>20 líneas o lógica repetida)
- Extract constant (magic numbers/strings)
- Rename for clarity
- Reduce nesting (early returns / guard clauses)
- Composition over inheritance
- Introduce parameter object (>3 params)
- Remove dead code (verificar con grep primero)