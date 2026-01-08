# Día 3 - Parte A

## Enunciado

<!-- Rellenar con el enunciado del problema -->

## Patrones de diseño

### Factory Method

Uso de `BatteryMaximizer.create()` para encapsular la creación de objetos.

### Builder Pattern con Fluent API

Implementación del patrón Builder que permite:

```java
BatteryMaximizer.create()
    .fromString(batteryList)
    .add(moreBatteries)
    .sum()
```

### Immutability con Records

`record BatteryBank(List<Integer> batteries)` proporciona:

-   Inmutabilidad automática
-   Thread-safety
-   Claridad semántica (es un contenedor de datos)

### Clean Code

-   **Encapsulación de lógica compleja**: El algoritmo de maximización está encapsulado en `BatteryBank.sum()`
-   **Nombres descriptivos**: `getMaxNum`, `joinChars` comunican claramente su propósito
-   **Métodos pequeños**: Cada método tiene una responsabilidad única

## Estructuras de datos

### List<BatteryBank>

`ArrayList<BatteryBank>` como contenedor principal, permitiendo:

-   Agregar banks dinámicamente
-   Stream processing para agregación
-   Modularidad (cada bank es independiente)

### List<Integer> (dentro de BatteryBank)

Lista de dígitos individuales que permite:

-   Sublists eficientes con `subList()`
-   Operaciones de stream para encontrar máximos
-   Acceso indexado para algoritmo recursivo

### Stream API

Uso intensivo para transformaciones:

```java
batteryBankList.stream()
    .map(String::trim)
    .map(bB -> new BatteryBank(...))
    .collect(Collectors.toList())
```

## Algoritmos aplicados

### Algoritmo Greedy para Maximización

El método `BatteryBank.sum()` implementa un **algoritmo greedy**:

```java
public int sum() {
    if (batteries.isEmpty()) return 0;
    if (batteries.size() == 1) return batteries.getFirst();
    if (batteries.size() == 2) return joinChars(first, last);

    return joinChars(
        getMaxNum(batteries.subList(0, batteries.size()-1)),
        getMaxNum(batteries.subList(indexOf(maxFromLeft)+1, size))
    );
}
```

**Estrategia**: Selecciona el dígito máximo de la parte izquierda, luego el máximo de la parte derecha (después del primer máximo), y los une.

### Casos Base Recursivos

El algoritmo maneja cases base explícitamente:

-   Lista vacía → 0
-   Un elemento → ese elemento
-   Dos elementos → concatenación directa

### Búsqueda de Máximo con Streams

```java
batteries.stream().max(Integer::compare).get()
```

Usa streams para encontrar el máximo eficientemente.

### Concatenación de Dígitos

`joinChars` convierte dos integers en su representación concatenada:

```java
Integer.parseInt(integer.toString() + integer1.toString())
```

## Interfaces

**No se utilizan interfaces**.

**Justificación**:

-   `BatteryMaximizer` tiene una implementación concreta única
-   `BatteryBank` es un record (no puede implementar lógica de interfaz compleja)
-   No hay necesidad de polimorfismo
-   El diseño es simple y directo

## El por qué de esas elecciones

### Record para BatteryBank

Un `record` es perfecto aquí porque:

-   Es principalmente un contenedor de datos con algo de lógica
-   La inmutabilidad previene bugs de compartición de estado
-   El código es más conciso que una clase tradicional

### Algoritmo Greedy

La elección de un algoritmo greedy (seleccionar máximos locales) sugiere que:

-   El problema permite optimización local
-   No se requiere backtrackingو
-   La solución is computacionalmente eficiente (no exhaustiva)

### Separación de Parsing y Lógica

`fromString` maneja toda la complejidad de parsing:

-   Split de strings
-   Conversión a integers
-   Creación de BatteryBank objects

Esto mantiene `sum()` enfocado solo en el algoritmo, respetando SRP.

### Stream Processing en fromString

El parsing usa un pipeline funcional:

```
String -> split -> map(parseInt) -> collect -> BatteryBank
```

Esto es:

-   Declarativo (qué, no cómo)
-   Componible (fácil agregar pasos)
-   Testeable (cada transformación es pura)

## Cualquier otro dato interesante

### Potencial Mejora: Validación

El código asume que `getMaxNum` siempre encuentra un elemento (`get()` sin manejo de `Optional`), lo que podría lanzar excepciones con listas vacías. Esto está protegido por los cases base, pero podría ser más explícito.

### Complejidad del Algoritmo

El algoritmo hace múltiples pasadas sobre sublistas:

-   `getMaxNum` es O(n)
-   Se llama dos veces por recursión
-   Complejidad total aproximada: O(n²) en el peor caso

### Uso de split("") para Parsing

```java
Arrays.stream(bB.split(""))
    .mapToInt(Integer::parseInt)
```

Divide un string en caracteres individuales, lo cual es elegante pero podría ser más eficiente con `toCharArray()`.

### Design Trade-off: Simplicidad vs Rendimiento

El código favorece **claridad sobre optimización**: usa streams, múltiples sublistas, y concatenación de strings en lugar de manipulación de bits. Esto es apropiado para problemas de AoC donde la legibilidad es más valiosa que microsegundos de performance.
