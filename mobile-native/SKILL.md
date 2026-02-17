---
activation: model_decision
name: mobile-native
description: "iOS, Android, React Native, Flutter. Se activa con desarrollo móvil, apps nativas."
---
# Mobile Engineering

## Seguridad
- Keychain (iOS) / Keystore (Android) para tokens
- NUNCA SharedPreferences/UserDefaults para secrets
- No sensitive data en logs (ni debug)
- Certificate pinning para high-security apps

## UX
- Offline-first: local DB + sync strategy
- Permisos: pedir cuando necesario, explicar por qué, fallback graceful
- Deep links: validar URLs entrantes