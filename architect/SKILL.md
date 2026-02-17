---
activation: model_decision
name: architect
description: "Diseño de sistemas, ADRs, análisis de trade-offs, diagramas. Se activa con arquitectura, system design, 'X vs Y'."
---
# Architecture & System Design

## ADR Process
1. CONTEXT — Problema, constraints, requirements
2. OPTIONS — 2-4 enfoques viables
3. ANALYSIS — Decision matrix con criterios ponderados
4. RECOMMENDATION — Ganador claro + justificación
5. DOCUMENT — Title, Date, Status, Context, Decision, Consequences

## Principios
- SOLID (SRP, OCP, LSP, ISP, DIP)
- Clean Architecture: Domain → Application → Infrastructure
- Dependencies flow INWARD. NEVER reverse.
- Composition over inheritance
- Dependency injection for external services

## Diagramas
- Mermaid: sequence, class, flowchart, C4, ER
- C4 model: Context → Container → Component → Code
- Incluir dirección de flujo de datos

## Workflow DDD (Domain-Driven Design)

Cuando implementes features siguiendo DDD, respeta este orden:

### 1. Domain Layer (Core)
- **Entities**: objetos con identidad única (User, Order, Product)
- **Value Objects**: objetos inmutables sin identidad (Email, Money, Address)
- **Domain Events**: eventos de negocio (UserRegistered, OrderPlaced)
- **Domain Services**: lógica que no pertenece a una entidad

**Reglas**:
- Sin dependencias externas (DB, HTTP, etc.)
- Solo lógica de negocio pura
- Validaciones de dominio aquí

### 2. Repository Interfaces (Domain)
- Definir contratos en domain layer
- Implementación en infrastructure layer
- Métodos de negocio, no CRUD genérico

```typescript
// domain/repositories/UserRepository.ts
interface UserRepository {
  findByEmail(email: Email): Promise<User | null>
  save(user: User): Promise<void>
  // NO: findById, update, delete (demasiado genérico)
}
```

### 3. Application Services (Use Cases)
- Orquestar domain entities y repositories
- Manejar transacciones
- Mapear domain → DTOs

```typescript
// application/services/RegisterUserService.ts
class RegisterUserService {
  constructor(
    private userRepo: UserRepository,
    private eventBus: EventBus
  ) {}

  async execute(dto: RegisterUserDTO): Promise<void> {
    // 1. Validar input
    // 2. Crear entidad de dominio
    // 3. Persistir via repository
    // 4. Publicar domain event
  }
}
```

### 4. Presentation Layer (Controllers/Routes)
- Validar request (Zod, Joi, etc.)
- Llamar application service
- Mapear resultado → HTTP response

```typescript
// api/routes/users.routes.ts
router.post('/users', async (req, res) => {
  const dto = validateRegisterUserDTO(req.body)
  await registerUserService.execute(dto)
  res.status(201).json({ message: 'User registered' })
})
```

## Checklist de Code Review Arquitectónico

Cuando revises código backend, verificar:

### Separación de capas
- [ ] Domain no depende de infrastructure
- [ ] Application no depende de presentation
- [ ] Repositories definidos como interfaces en domain
- [ ] Implementaciones de repositories en infrastructure

### Validación
- [ ] Input validation en presentation layer (Zod/Joi)
- [ ] Business validation en domain layer
- [ ] No validación duplicada

### Manejo de errores
- [ ] Errores de dominio tipados (DomainError, ValidationError)
- [ ] Mapeo error domain → HTTP en presentation
- [ ] No exponer stack traces en producción

### Transacciones
- [ ] Transacciones manejadas en application layer
- [ ] Rollback automático en caso de error
- [ ] No transacciones anidadas sin justificación

### Testing
- [ ] Domain entities testeables sin DB
- [ ] Application services con mocks de repositories
- [ ] Integration tests para repositories

## Mapeo Error Domain → HTTP

| Domain Error | HTTP Status | Ejemplo |
|--------------|-------------|---------|
| ValidationError | 400 Bad Request | Email inválido |
| NotFoundError | 404 Not Found | Usuario no existe |
| ConflictError | 409 Conflict | Email ya registrado |
| UnauthorizedError | 401 Unauthorized | Token inválido |
| ForbiddenError | 403 Forbidden | Sin permisos |
| DomainError | 422 Unprocessable Entity | Regla de negocio violada |

## Anti-patterns a evitar

### ❌ Anemic Domain Model
Entities sin comportamiento, solo getters/setters. Toda la lógica en services.

**Mal**:
```typescript
class User {
  constructor(public email: string, public password: string) {}
}

// Lógica en service
userService.validateEmail(user.email)
```

**Bien**:
```typescript
class User {
  private constructor(private email: Email, private password: HashedPassword) {}

  static create(email: string, password: string): User {
    // Validación aquí
    return new User(Email.create(email), HashedPassword.create(password))
  }
}
```

### ❌ God Service
Service que hace demasiado. Dividir en use cases específicos.

### ❌ Leaky Abstractions
Exponer detalles de implementación (Prisma models, TypeORM entities) fuera de infrastructure.