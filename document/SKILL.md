---
name: document
description: "Genera documentación en formato apropiado. Se activa con 'document', 'README', 'API docs', 'JSDoc'."
activation: always_on
---
# Documentation Generator

## Formatos
- JSDoc/TSDoc para TypeScript/JavaScript
- Google-style docstrings para Python
- README: purpose, setup, commands, architecture
- ADR: Title, Date, Status, Context, Decision, Consequences
- OpenAPI/Swagger para APIs

## Reglas
- Documenta el POR QUÉ, no el QUÉ
- Params: nombre, tipo, descripción
- Return: tipo y descripción
- Excepciones: qué lanza y cuándo
- Ejemplo: para APIs complejas o no obvias