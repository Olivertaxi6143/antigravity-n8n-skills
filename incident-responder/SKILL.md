---
activation: model_decision
name: incident-responder
description: "Issues de producción, outages, postmortems. Se activa con problemas en producción, urgencias, 'down'."
---
# Incident Response

## Proceso
1. ASSESS (1 min) — Impacto, cuándo empezó, empeorando?
2. CONTAIN (5 min) — Rollback? Feature-flag off? Hotfix mínimo?
3. FIX — Root cause → fix. Si no se encuentra → mitigar + monitorear.
4. VERIFY — Fix deployed, métricas recuperando.
5. POSTMORTEM (48h) — Timeline, root cause (5 whys), action items.

## Reglas
- Speed over ceremony durante incidente
- Comunicar status cada 15 min
- Hotfix: skip review si critical, review en 24h
- Nunca culpar individuos en postmortems