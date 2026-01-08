# Día 2 - Parte B

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

### Factory Method

Implementación del patrón **Factory Method** consistente con la Parte A.

### Fluent API (Builder Pattern)

Interfaz fluida para configuración de objetos con método chaining.

### Composition

`ClassifierAdder` compone múltiples instancias de `Classifier`.

### Clean Code

-   Métodos pequeños y cohesivos
-   Nombres descriptivos que comunican propósito
-   Separación clara de parsing y lógica de negocio

## Estructuras de datos

Mismas estructuras que la Parte A:

-   `List<ID>` para almacenar IDs inválidos
-   `List<Classifier>` para composición
-   `LongStream` para generación eficiente de rangos
-   `record ID` para encapsulación inmutable

## Algoritmos aplicados

Los mismos algoritmos que la Parte A:

-   Validación de ID con reglas de inicio y mitades
-   Generación lazy de rangos
-   Filtrado early para eficiencia de memoria

## Interfaces

**No se utilizan interfaces** por las mismas razones que la Parte A:

-   No hay necesidad de polimorfismo
-   Implementaciones concretas únicas
-   YAGNI principle

## El por qué de esas elecciones

Las elecciones arquitectónicas son idénticas a la Parte A, ya que el problema es estructuralmente similar.

### Reutilización de Código

La Parte B aprovecha exactamente la misma implementación que la Parte A, demostrando que el diseño inicial era suficientemente flexible y genérico.

### Sin Necesidad de Modificación

El hecho de que no se requieran cambios en el código para la Parte B valida el principio **Open/Closed**: el código está abierto para extensión (puede usarse con diferentes inputs) pero cerrado para modificación.

## Cualquier otro dato interesante

### Código Idéntico

Es notable que las Partes A y B compartan el mismo código exacto. Esto sugiere que:

-   El problema varía en los datos de entrada, no en el algoritmo
-   El diseño fue lo suficientemente abstracto desde el inicio
-   No se necesitó refactoring entre partes

### Diseño Anticipatorio Exitoso

El diseño original anticipó correctamente las necesidades, evitando:

-   Duplicación de código
-   Refactoring entre partes
-   Breaking changes en la API

### Validación del Diseño

Que el mismo código resuelva ambas partes es una fuerte validación de que:

-   Las abstracciones están en el nivel correcto
-   La separación de responsabilidades es adecuada
-   El código es suficientemente genérico sin ser over-engineered
