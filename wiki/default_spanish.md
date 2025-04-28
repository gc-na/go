<!--
Meta Description: # Uso de "default" en Go: Guía Completa ## Sinopsis En Go, la palabra clave `default` se utiliza en las declaraciones de `switch` y en la inicializaci...
Meta Keywords: por, defecto, default, valor, switch
-->

# Uso de "default" en Go: Guía Completa

## Sinopsis
En Go, la palabra clave `default` se utiliza en las declaraciones de `switch` y en la inicialización de valores por defecto para tipos de datos. Esta funcionalidad permite manejar casos específicos y establecer valores predeterminados en el lenguaje de programación Go.

## Documentación
El `default` en Go cumple funciones clave en diferentes contextos:

### En sentencias `switch`
El `default` se emplea como una cláusula opcional en las sentencias `switch` para manejar situaciones donde ninguna de las expresiones coincidentes se cumple. Esto proporciona una forma de controlar el flujo del programa de manera efectiva.

**Sintaxis:**
```go
switch variable {
case valor1:
    // acción para valor1
case valor2:
    // acción para valor2
default:
    // acción si no coincide con ningún caso
}
```

### En inicialización de valores
En Go, los tipos primitivos tienen valores por defecto. Por ejemplo, el valor por defecto de un entero es `0`, el de un booleano es `false`, y el de un string es `""` (cadena vacía). Esto es útil para asegurar que las variables siempre tengan un valor definido al ser declaradas.

## Ejemplos
### Ejemplo de `default` en switch
```go
package main

import (
    "fmt"
)

func main() {
    dia := "Lunes"

    switch dia {
    case "Martes":
        fmt.Println("Hoy es Martes")
    case "Miércoles":
        fmt.Println("Hoy es Miércoles")
    default:
        fmt.Println("No es Martes ni Miércoles")
    }
}
```
**Salida:**
```
No es Martes ni Miércoles
```

### Ejemplo de valor por defecto
```go
package main

import (
    "fmt"
)

func main() {
    var numero int
    var estado bool
    var texto string

    fmt.Println("Valor por defecto de numero:", numero) // 0
    fmt.Println("Valor por defecto de estado:", estado) // false
    fmt.Println("Valor por defecto de texto:", texto)   // ""
}
```
**Salida:**
```
Valor por defecto de numero: 0
Valor por defecto de estado: false
Valor por defecto de texto: 
```

## Explicación
Es importante tener en cuenta que en Go, si se omite un caso en un `switch`, el flujo del programa continúa a través de la cláusula `default` si está presente. Si no hay un caso que coincida y tampoco hay un `default`, el programa no ejecutará ninguna acción relacionada con la sentencia `switch`.

Además, al declarar variables, siempre se les asigna un valor por defecto, lo que puede ser útil para evitar errores en caso de que se utilicen antes de ser inicializadas explícitamente. Sin embargo, hay que estar atento a qué tipo de dato se está utilizando, para evitar confusiones con los valores por defecto.

## Resumen en una línea
La palabra clave `default` en Go se utiliza en sentencias `switch` para manejar casos no especificados y también para definir valores por defecto en tipos de datos.