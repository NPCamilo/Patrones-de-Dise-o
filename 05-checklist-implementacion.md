# Checklist Ponytail para implementar State

Antes de escribir código, responde esto:

- [ ] ¿Tengo un objeto cuyo comportamiento cambie según un estado interno?
- [ ] ¿Tengo condicionales `if/estado` o `switch/estado` repetidos en varios métodos?
- [ ] ¿Tendré al menos 3 estados, o la lógica va a crecer?
- [ ] ¿Puedo permitirme crear una clase por estado?

Si respondiste **no** a cualquiera de las dos primeras, usa un simple `if` y no implementes State.

## Pasos mínimos (sobre-ingeniería cero)

1. Crea la interfaz/base `Estado` con los métodos que varían.
2. Crea una clase concreta por estado.
3. Crea el `Context` que referencia al estado actual y delega.
4. Cada `ConcreteState` cambia `context.estado = new OtroEstado()` cuando corresponde.
5. Prueba el camino feliz y una transición inválida.

## Riesgos a conocer (lo que no revisé)

- No validé que tu lenguaje soporte herencia o composición de la forma que muestra el ejemplo.
- No agregué manejo de hilos (concurrencia). Si varios hilos cambian el estado al mismo tiempo, necesitas sincronización.
- No agregué persistencia. Si necesitas guardar estados en base de datos, eso es aparte del patrón.
