# Grafo de relaciones entre patrones de comportamiento

Diagrama Mermaid. Úsalo para visualizar cómo se conecta State con el resto.

```mermaid
graph TD
    subgraph Comportamiento
        A[State]
        B[Strategy]
        C[Observer]
        D[Command]
        E[Memento]
        F[Iterator]
        G[Mediator]
        H[Visitor]
        I[Interpreter]
        J[Chain of Responsibility]
        K[Template Method]
    end

    A -->|estructura similar, intención distinta| B
    A -->|dispara al cambiar| C
    A -->|guarda/restaura estados| E
    A -->|transiciones deshacibles| D
    B -->|alternativa cuando el cliente elige| A
    C -->|notifica cambio de estado| A
    E -->|captura estado para State| A
    D -->|encapsula transición| A

    style A fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    style B fill:#fff3e0,stroke:#e65100,stroke-width:1px
    style C fill:#f3e5f5,stroke:#4a148c,stroke-width:1px
```

## Cómo leerlo

- **State (A)** es el nodo central de esta sesión.
- Su relación más fuerte es con **Strategy (B)**: comparten estructura, difieren en quién decide.
- Se conecta con **Observer (C)** si necesitas avisar a otros módulos al cambiar de estado.
- Se conecta con **Memento (E)** y **Command (D)** si necesitas historial o deshacer.
