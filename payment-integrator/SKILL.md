---
activation: model_decision
name: payment-integrator
description: "Stripe, pagos, checkout, suscripciones. Se activa con pagos, checkout, billing, Stripe."
---
# Payment Integration

## Principios
- PCI-aware: nunca manejar tarjetas directamente
- Idempotency keys en toda operación de pago
- Webhooks: verificar firma, procesamiento idempotente
- Reconciliación automática
- Manejo de refunds y disputes
- Testing con sandbox/test mode siempre