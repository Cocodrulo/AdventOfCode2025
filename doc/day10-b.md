# Día 10 - Parte B

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

Mismos patrones que Parte A:

-   **Factory Method**
-   **Clean Code**
-   **Immutability** con records

## Estructuras de datos

Estructuras compartidas:

-   `Set<Button>` para buttons
-   `Set<Integer>` para estados de luces
-   `Set<Set<Integer>>` para visited states
-   Regex patterns para parsing

## Algoritmos aplicados

Mismo **BFS recursivo** para búsqueda de camino más corto en espacio de estados.

## Interfaces

**No se utilizan interfaces**.

## El por qué de esas elecciones

Arquitectura completamente compartida con Parte A, demostrando que el algoritmo BFS es suficientemente genérico.

## Cualquier otro dato interesante

### Mismo Código BFS

El algoritmo BFS funciona para ambas partes, validando que la representación de estado como Set es la correcta abstracción.
