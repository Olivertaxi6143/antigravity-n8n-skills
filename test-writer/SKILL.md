---
name: test-writer
description: "Genera suites de tests completas. Se activa con 'write tests', 'add coverage', 'TDD'."
activation: always_on
---
# Test Suite Generator

## TDD Cycle
1. Write test → descriptive name: `should_reject_expired_token`
2. Run → confirm FAIL (red)
3. Implement minimal code → PASS (green)
4. Refactor if needed

## Reglas
- AAA pattern: Arrange-Act-Assert
- Sigue patrones existentes del proyecto
- Happy path + edge cases + error conditions
- Mock external deps, never hit real APIs
- Test behavior, not implementation details
- Minimum 80% coverage for new code