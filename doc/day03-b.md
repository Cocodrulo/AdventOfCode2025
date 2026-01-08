# Día 3 - Parte B

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

Mismos patrones que la Parte A:

-   **Factory Method** con `create()`
-   **Fluent API** para method chaining
-   **Immutability** con records
-   **Clean Code** con métodos cohesivos

## Estructuras de datos

Estructuras idénticas a la Parte A:

-   `List<BatteryBank>` como contenedor
-   `List<Integer>` dentro de cada BatteryBank
-   Stream API para procesamiento funcional

## Algoritmos aplicados

El mismo **algoritmo greedy** que la Parte A para seleccionar y combinar dígitos máximos.

## Interfaces

**No se utilizan interfaces** por las mismas razones que la Parte A.

## El por qué de esas elecciones

Las elecciones arquitectónicas son idénticas a la Parte A.

### Reutilización de Diseño

La Parte B reutiliza completamente la arquitectura de la Parte A, indicando un diseño robusto y genérico.

## Datos Interesantes

### Código Compartido

Ambas partes comparten el mismo código, sugiriendo que:

-   El problema varía en datos de entrada, no en lógica
-   El diseño inicial previó las necesidades correctamente
-   No se requirió refactoring entre partes

### Validación del Algoritmo Greedy

Que el algoritmo greedy funcione para ambas partes valida que la estrategia de optimización local es correcta para este tipo de problema.
