# Patrón State (Estado)

## Qué es

State permite que un objeto cambie su comportamiento cuando su estado interno cambia. Parece que el objeto cambió de clase.

## Analogía real

Piensa en una **máquina expendedora**:

- Estado "Sin dinero": no entrega producto.
- Estado "Dinero insertado": acepta selección de producto.
- Estado "Producto dispensado": entrega el producto y vuelve a "Sin dinero".

La máquina es el mismo objeto, pero su comportamiento depende del estado en el que esté.

## Cuándo usarlo (Ponytail: solo si necesitas esto)

Usa State cuando:

1. Un objeto tiene un comportamiento que depende de su estado.
2. Tiene condicionales grandes (`if / else` o `switch`) que cambian según un campo tipo `estado`.
3. Quieres evitar que esas condiciones se esparzan por todo el código.

**No uses State si solo tienes 2 estados que nunca cambian.** Un simple `if` es suficiente y menos código.

## Participantes

| Participante | Rol |
|--------------|-----|
| **Context** | El objeto principal (ej. `Pedido`, `MáquinaExpendedora`). Tiene una referencia al estado actual y delega en él. |
| **State** | Interfaz o clase base que declara los métodos comunes a todos los estados. |
| **ConcreteState** | Implementaciones concretas de cada estado (ej. `EstadoPendiente`, `EstadoPagado`). |

## Consecuencias

- **Bueno:** Elimina condicionales gigantes. Cada estado vive en su propia clase.
- **Bueno:** Fácil de agregar nuevos estados sin tocar el Context (principio Abierto/Cerrado).
- **Costo:** Más clases. Si tienes solo 2 o 3 estados simples, puede ser sobre-ingeniería.

## Relación mínima con tu lista de comportamiento

State es el primo cercano de **Strategy** (nº 21). La diferencia:

- **Strategy:** el cliente elige qué algoritmo usar.
- **State:** el estado interno del objeto dicta el comportamiento, y el objeto puede cambiar de estado solo.
