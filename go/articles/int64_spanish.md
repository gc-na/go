<!--
Meta Description: # int64 en Go: Tipos de Datos Enteros de 64 Bits ## Sinopsis El tipo de dato `int64` en Go es un tipo numérico que representa enteros de 64 bits con s...
Meta Keywords: int64, que, var, tipos, enteros
-->

# int64 en Go: Tipos de Datos Enteros de 64 Bits

## Sinopsis
El tipo de dato `int64` en Go es un tipo numérico que representa enteros de 64 bits con signo. Se utiliza para almacenar valores enteros grandes, permitiendo un rango que va desde -9,223,372,036,854,775,808 hasta 9,223,372,036,854,775,807.

## Documentación
`int64` es parte de los tipos de datos primitivos en Go, específicamente en el paquete `builtin`. Este tipo de dato es especialmente útil cuando se requiere una mayor capacidad que los tipos enteros de menor tamaño, como `int` o `int32`. El tamaño de `int64` es fijo, lo que asegura que los valores ocupen la misma cantidad de memoria en todas las plataformas, facilitando la portabilidad.

### Propósito
El propósito de `int64` es proporcionar una representación de enteros que pueda manejar cálculos y operaciones que involucren grandes números sin riesgo de desbordamiento.

### Uso
Para declarar una variable de tipo `int64`, simplemente se utiliza la palabra clave `int64` seguida del nombre de la variable. Por ejemplo:

```go
var numero int64 = 9223372036854775807
```

También se puede utilizar la función `int64()` para convertir otros tipos numéricos a `int64`:

```go
var numero float64 = 3.14
var entero int64 = int64(numero)
```

## Ejemplos

### Ejemplo 1: Declaración y asignación
```go
package main

import "fmt"

func main() {
    var a int64 = 10000000000
    fmt.Println(a) // Imprime: 10000000000
}
```

### Ejemplo 2: Conversión de tipos
```go
package main

import "fmt"

func main() {
    var b float64 = 12345.67
    var c int64 = int64(b)
    fmt.Println(c) // Imprime: 12345
}
```

### Ejemplo 3: Operaciones aritméticas
```go
package main

import "fmt"

func main() {
    var x int64 = 10
    var y int64 = 20
    var suma int64 = x + y
    fmt.Println(suma) // Imprime: 30
}
```

## Explicación
Al trabajar con `int64`, es importante tener en cuenta algunos puntos:

- **Desbordamiento**: Al igual que otros tipos de datos numéricos, `int64` puede desbordarse si se excede su capacidad máxima. Por ejemplo, intentar almacenar un valor mayor a `9,223,372,036,854,775,807` resultará en un comportamiento inesperado.
- **Conversión de tipos**: Al convertir de `float64` a `int64`, se pierde la parte decimal. Esto puede llevar a problemas si no se maneja adecuadamente.
- **Compatibilidad de plataforma**: Aunque `int64` es un tipo de longitud fija, el tipo `int` varía en función de la arquitectura de la máquina. Para asegurar la portabilidad, es recomendable usar `int64` si se espera trabajar con grandes números.

## Resumen en una línea
`int64` es un tipo de dato en Go que representa enteros de 64 bits, ideal para almacenar y manipular grandes números enteros.