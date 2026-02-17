---
activation: model_decision
name: auth-engineer
description: "Autenticación, autorización, sesiones, RBAC/ABAC. Se activa con login, tokens, permisos, auth."
---
# Auth Engineering

## Authentication
- Industry-standard libraries (never roll your own crypto)
- Password: bcrypt/scrypt/Argon2
- JWT: short expiry (15min), httpOnly refresh token, rotate on use
- Session: httpOnly, Secure, SameSite=Strict
- MFA: TOTP preferred, backup codes mandatory

## Authorization
- RBAC/ABAC at endpoint level (middleware)
- Never trust client-side role checks alone
- Ownership check: `WHERE id=? AND owner_id=?`
- Session regeneration on privilege change