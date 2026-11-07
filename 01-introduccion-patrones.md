# Introducción a los patrones de diseño

## Definición

Un patrón de diseño es una solución reutilizable a un problema común dentro de un contexto específico. No es código copiado y pegado; es una plantilla que describes y adaptas a tu caso.

## Las 3 familias (según tu imagen)

| Familia | Qué resuelve | Ejemplos de tu lista |
|---------|--------------|----------------------|
| **Creacional** | Cómo crear objetos sin acoplarse a clases concretas | Singleton, Factory Method, Builder |
| **Estructural** | Cómo componer clases y objetos para formar estructuras más grandes | Adapter, Decorator, Proxy, Composite |
| **Comportamiento** | Cómo se comunican y reparten responsabilidades los objetos | **State**, Strategy, Observer, Command |

## Por qué te conviene enfocarte en Comportamiento

Los patrones creacional y estructural afectan principalmente a cómo se construye y se organiza el código. Los de comportamiento afectan directamente a **cómo fluye la lógica de negocio**, que es donde más se nota la diferencia entre código difícil de mantener y código flexible.

El patrón **State** pertenece a esta familia porque modela el comportamiento de un objeto que cambia según su estado interno.
