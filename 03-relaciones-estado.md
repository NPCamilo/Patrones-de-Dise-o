# Relaciones de State con otros patrones

Esto te sirve para decidir cuándo combinar patrones en tus proyectos.

## State ↔ Strategy (la relación más importante)

| Aspecto | State | Strategy |
|---------|-------|----------|
| ¿Quién decide el comportamiento? | El objeto mismo, según su estado interno | El cliente, desde afuera |
| ¿Cambia durante la ejecución? | Sí, el objeto transita entre estados | Generalmente no, el cliente lo fija |
| Estructura | Muy similar (ambos delegan en objetos separados) | Muy similar |

**Regla práctica:** si el comportamiento depende de un estado que el objeto gestiona solo → usa **State**. Si el comportamiento lo elige el usuario o el cliente → usa **Strategy**.

## State ↔ Observer

- Un cambio de estado en State puede **notificar** a observadores.
- Ejemplo: un pedido pasa de `Pendiente` a `Pagado` y se notifica al módulo de envíos.

## State ↔ Memento

- Si necesitas guardar y restaurar estados anteriores (deshacer/rehacer en una máquina de estados), usa **Memento** para capturar el estado sin romper encapsulamiento.

## State ↔ Command

- Puedes encapsular cada transición de estado como un objeto `Command`, lo que permite registrar transiciones y hacer undo/redo.

## Grafo de relaciones (texto)

```
Comportamiento
├── State
│   ├── usa Strategy (estructura similar, intención distinta)
│   ├── dispara Observer (al cambiar de estado)
│   ├── combina con Memento (guardar/restaurar estados)
│   └── combina con Command (transiciones deshacibles)
├── Strategy
├── Observer
├── Command
├── Memento
└── ... (los demás de tu lista: Iterator, Mediator, Visitor, etc.)
```

> Ponytail: no implementes todas estas relaciones a la vez. Implementa State solo. Agrega Observer solo cuando necesites notificar algo al cambiar de estado.
