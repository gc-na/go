<!--
Meta Description: # Uso de "case" en Go: Estructuras de Control en el Lenguaje de Programación Go ## Sinopsis El comando `case` en Go se utiliza dentro de la estructura...
Meta Keywords: case, switch, código, expresión, fmt
-->

# Uso de "case" en Go: Estructuras de Control en el Lenguaje de Programación Go

## Sinopsis
El comando `case` en Go se utiliza dentro de la estructura de control `switch` para evaluar múltiples condiciones y ejecutar bloques de código específicos según el valor de una expresión. Esta característica permite simplificar la toma de decisiones en el código, mejorando su legibilidad y eficiencia.

## Documentación
La estructura `switch` en Go ofrece una manera versátil de manejar múltiples condiciones de forma más clara que utilizando múltiples sentencias `if`. Cada `case` dentro de un `switch` representa una posible coincidencia con el valor de la expresión evaluada.

### Propósito
El propósito del `case` es permitir que los desarrolladores evalúen una expresión y ejecuten diferentes bloques de código según el resultado de esa evaluación. Esto es útil en situaciones donde se necesita tomar decisiones basadas en el valor de una variable.

### Uso
Un `switch` en Go puede tener múltiples `case`. La sintaxis básica es la siguiente:

```go
switch expresión {
case valor1:
    // código a ejecutar si expresión == valor1
case valor2:
    // código a ejecutar si expresión == valor2
default:
    // código a ejecutar si no hay coincidencias
}
```

### Detalles
- Un `switch` puede omitir la expresión; en este caso, se evalúa como `true`.
- Los `case` pueden utilizar valores constantes, variables o incluso expresiones complejas.
- Se puede usar `fallthrough` para ejecutar el siguiente `case` sin comprobar su condición, aunque esta característica debe utilizarse con precaución.

## Ejemplos

### Ejemplo básico de `switch` con `case`
```go
package main

import "fmt"

func main() {
    dia := "Lunes"

    switch dia {
    case "Lunes":
        fmt.Println("Hoy es Lunes")
    case "Martes":
        fmt.Println("Hoy es Martes")
    default:
        fmt.Println("No es un día de la semana conocido")
    }
}
```

### Ejemplo de `switch` sin expresión
```go
package main

import "fmt"

func main() {
    numero := 2

    switch {
    case numero < 0:
        fmt.Println("Número negativo")
    case numero == 0:
        fmt.Println("Número cero")
    case numero > 0:
        fmt.Println("Número positivo")
    }
}
```

## Explicación
Al usar `case`, es importante recordar que:
- Las comparaciones son estrictas; si el tipo de datos no coincide, no habrá coincidencia.
- Si múltiples `case` coinciden con el mismo valor, solo se ejecutará el bloque del primer `case` que coincida.
- Evita el uso excesivo de `fallthrough`, ya que puede llevar a una ejecución no deseada de bloques de código.

## Resumen en una línea
El comando `case` en Go permite evaluar múltiples condiciones en estructuras `switch`, facilitando la toma de decisiones en el código.