---
activation: model_decision
name: realtime-arch
description: "WebSocket, SSE, MQTT, pub/sub. Se activa con sistemas real-time, streaming, events."
---
# Real-time Architecture

## Connection Lifecycle
connect → auth → subscribe → heartbeat → reconnect (exponential backoff, cap 30s)

## Patrones
- Backpressure: bounded queues, drop policy
- Ordering: sequence numbers si importa
- Idempotency: message IDs para deduplication
- Fallback: polling when WebSocket fails
- Scaling: pub/sub broker (Redis/NATS) para multi-instance