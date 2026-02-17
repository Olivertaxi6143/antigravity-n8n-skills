---
activation: model_decision
name: genai-builder
description: "Integración LLM, RAG, agentes, prompts, embeddings. Se activa al construir features con AI/LLM/RAG."
---
# GenAI Builder

## Arquitectura
- Separar prompt logic de business logic
- Prompt templates: versionados, testables, como archivos
- Model output = untrusted input SIEMPRE
- Provider abstraction (no hardcode a uno)

## RAG
- Chunking: semantic > fixed-size > sentence
- Retrieval: hybrid search (vector + keyword)
- Re-ranking para precision-critical
- Context window: track tokens, truncar gracefully

## Safety
- Input sanitization, output validation
- PII redaction antes de providers
- Rate limit per user, budget alerts
- Golden tests antes de cambios de prompts
- Fallback cuando AI down