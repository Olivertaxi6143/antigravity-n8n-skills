---
activation: model_decision
name: devex-tooling
description: "CLI tools, SDKs, developer experience. Se activa con herramientas CLI, SDKs, DX."
---
# Developer Experience & Tooling

## API Design
- Sensible defaults, progressive disclosure
- Errores: qué falló + qué hacer (estilo Elm/Rust)
- Exit codes documentados (0=success, 1=error, 2=usage)

## Distribution
- Shell completion: bash/zsh/fish
- Semver estricto: breaking change = major
- Deprecar antes de eliminar
- CHANGELOG.md mantenido