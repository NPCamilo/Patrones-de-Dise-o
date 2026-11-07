# Glosario — Patrones de Comportamiento y State

Vocabulario canónico para este teaching workspace. Todos los materiales deben usar estos términos.

## Terms

**Patrón de diseño**:
Solución reutilizable a un problema común dentro de un contexto específico.
_Avoid_: Receta de cocina, plantilla de código copiado y pegado.

**Patrón de comportamiento**:
Familia de patrones que modelan cómo se comunican y reparten responsabilidades los objetos.
_Avoid_: Patrones de estructura, patrones de creación.

**State (Estado)**:
Patrón que permite a un objeto cambiar su comportamiento cuando su estado interno cambia, delegando en objetos de estado separados.
_Avoid_: Máquina de estados finitos (aunque esté relacionado, no es sinónimo).

**Context**:
Objeto principal que mantiene una referencia al estado actual y delega las operaciones en él.
_Avoid_: Clase principal, objeto anfitrión.

**ConcreteState**:
Implementación concreta de un estado específico dentro del patrón State.
_Avoid_: Estado, simplemente.

**Strategy**:
Patrón de comportamiento donde el cliente elige qué algoritmo usar, a diferencia de State donde el objeto mismo dicta el comportamiento según su estado.
_Avoid_: Estado (son conceptos distintos aunque se parecen estructuralmente).

**Observer**:
Patrón que permite notificar a varios objetos cuando el estado de otro cambia.
_Avoid_: Publicador-suscriptor (término genérico, no el patrón GOF específico).
