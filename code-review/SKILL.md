---
name: code-review
description: "Analiza código para bugs, seguridad, estilo y arquitectura. Se activa con 'review', 'PR', 'check my code'."
activation: always_on
---
# Code Review

## Proceso
1. UNDERSTAND — Qué hace el cambio
2. STRUCTURE — Cambios coherentes, sin mezcla
3. CORRECTNESS — Edge cases, race conditions, resource leaks
4. SECURITY — Gate checks (§6.1)
5. TESTING — Cobertura y legibilidad
6. MAINTAINABILITY — Naming, complejidad, magic numbers

## Output
- 🔴 BLOCKER: bugs, security, data loss
- 🟡 SUGGESTION: readability, edge cases
- 🟢 NIT: style, naming
- 💡 PRAISE: good patterns
Veredicto: APPROVE / REQUEST CHANGES / NEEDS DISCUSSION