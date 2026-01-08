# Día 7 - Parte B

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

Mismos patrones que la Parte A:

-   **Singleton** con lazy initialization
-   **Factory Method**
-   **Fluent API**

## Estructuras de datos

Estructuras compartidas con la Parte A:

-   `List<Beam>` para almacenamiento de beams
-   IntStream para procesamiento

## Algoritmos aplicados

Mismos algoritmos de construcción iterativa y procesamiento por niveles.

## Interfaces

**No se utilizan interfaces**.

## El por qué de esas elecciones

Arquitectura compartida con la Parte A.

## Cualquier otro dato interesante

### Mismo Singleton

La Parte B reutiliza el mismo singleton, lo que significa que debe llamarse `resetInstance()` entre partes o usar instancias separadas.
