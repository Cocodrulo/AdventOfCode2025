# Día 11 - Parte B

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

Mismos patrones que Parte A:

-   **Factory Method**
-   **Memoization** para optimización
-   **Clean Code**
-   **Records** para value objects

## Estructuras de datos

Estructuras compartidas:

-   `Set<Device>` para dispositivos
-   `Map<Device, Long>` para cache
-   Grafo implícito a través de outputs

## Algoritmos aplicados

Mismo **DFS recursivo con memoization** para conteo de caminos.

Posiblemente con **cache adicional** (`CacheKey`, `VisitedSet`) para optimizaciones más avanzadas.

## Interfaces

**No se utilizan interfaces**.

## El por qué de esas elecciones

Arquitectura compartida con Parte A.

### Optimizaciones Adicionales

La Parte B introduce `CacheKey` y `VisitedSet`, sugiriendo:

-   Cache más sofisticado
-   Posible tracking de estados visitados
-   Optimizaciones para problemas más grandes

## Datos Interesantes

### Extensión delMemoization

La introducción de estructuras adicionales muestra cómo el patrón Memoization puede extenderse para problemas más complejos.
