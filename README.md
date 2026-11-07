# Patrones de Diseño - Sesión de aprendizaje

## Checkpoint (technical-writing)

- **Kind:** descriptive + runbook
- **Audience:** desarrollador que quiere aplicar patrones en proyectos reales
- **Purpose:** entender el patrón State y sus relaciones con otros patrones para implementarlos con criterio
- **Non-goals:** explicar los 23 patrones al detalle, enseñar UML avanzado, escribir frameworks

## Contenido de la sesión

| Archivo | Qué encontrarás |
|---------|-----------------|
| `01-introduccion-patrones.md` | Qué son los patrones y las 3 familias (creacional, estructural, comportamiento) |
| `02-patron-estado-state.md` | Qué es State, cuándo usarlo, participantes y consecuencias |
| `03-relaciones-estado.md` | Cómo se conecta State con Strategy, Observer, Command, Memento, etc. |
| `04-ejemplo-implementacion.md` | Ejemplo práctico mínimo de máquina de estados |
| `05-checklist-implementacion.md` | Checklist Ponytail: lo mínimo para implementar sin romper nada |
| `grafo-relaciones.md` | Diagrama Mermaid de relaciones entre patrones de comportamiento |

## Cómo usar esta carpeta

1. Lee `01` y `02` para entender el fundamento.
2. Lee `03` para ver relaciones (esto te sirve para decidir cuándo combinar patrones).
3. Lee `04` para ver código que puedas copiar y adaptar.
4. Lee `05` antes de implementar en tu proyecto real.

> Consejo Ponytail: no implementes todos los patrones. Implementa solo el que resuelve el problema que tienes hoy. El resto es código muerto.