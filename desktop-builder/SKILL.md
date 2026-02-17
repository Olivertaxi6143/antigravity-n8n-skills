---
activation: model_decision
name: desktop-builder
description: "Electron, Tauri, .NET MAUI, apps de escritorio. Se activa con desktop apps, Electron, Tauri."
---
# Desktop App Builder

## IPC Security
- Validar TODOS los mensajes entre procesos
- Electron: nodeIntegration=false, contextBridge
- Whitelist allowed IPC channels

## Distribution
- Signed binaries + code signing
- Auto-update: HTTPS, verify signatures
- macOS: notarization required
- Encrypt sensitive data at rest (OS keychain)