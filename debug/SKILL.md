---
name: debug
description: "Análisis sistemático de bugs. Se activa con errores, stack traces, 'no funciona', comportamiento inesperado."
activation: always_on
---
# Debug & Root Cause Analysis

## Proceso
1. REPRODUCE — Confirmar bug: error, pasos, entorno
2. ISOLATE — Narrow down: grep, git blame, binary search
3. ROOT CAUSE — Causa real, no síntoma. Documentar: happening vs should happen
4. FIX — Cambio mínimo, no arreglar adjacent issues
5. TEST — Regression test que habría capturado esto
6. VERIFY — Suite completa + validación manual