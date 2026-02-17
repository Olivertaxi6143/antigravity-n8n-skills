---
activation: model_decision
name: frontend-craft
description: "Componentes UI, CSS, accesibilidad, responsive. Se activa con UI, componentes, estilos, frontend."
---
# Frontend Engineering

## Accesibilidad
- Semantic HTML: header, main, nav, section, article, footer
- ARIA solo cuando semantic HTML insuficiente
- Keyboard navigation para todo interactivo
- Color contrast >= 4.5:1 (WCAG AA)
- Alt text para imágenes significativas

## Performance
- Lazy-load below-fold content
- Code splitting por ruta
- Memoización: React.memo, useMemo para cómputos costosos
- Clean up listeners/intervals on unmount

## Patrones
- Composición sobre herencia
- Custom hooks para lógica reutilizable
- Controlled components por defecto