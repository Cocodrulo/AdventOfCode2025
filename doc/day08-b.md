# Día 8 - Parte B

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

Mismos patrones que la Parte A:

-   **Factory Method**
-   **Fluent API**
-   **Records** para value objects

## Estructuras de datos

Estructuras compartidas:

-   `List<Position>` (3D)
-   `List<JunctionBoxPair>`
-   CircuitSet para gestión de conexiones

## Algoritmos aplicados

Mismos algoritmos:

-   Generación de pares O(n²)
    -Ordenamiento por distancia
-   Algoritmo greedy para selección

## Interfaces

**No se utilizan interfaces**.

## El por qué de esas elecciones

Arquitectura compartida con la Parte A.

## Datos Interesantes

### Código Reutilizado

Implementación idéntica, variando parámetros o criterios de cálculo final.
