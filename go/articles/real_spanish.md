<!--
Meta Description: # "real" en Go: Entendiendo el tipo de dato real ## Sinopsis El tipo de dato "real" en Go se refiere a los números de punto flotante, que son utilizad...
Meta Keywords: números, tipo, que, precisión, los
-->

# "real" en Go: Entendiendo el tipo de dato real

## Sinopsis
El tipo de dato "real" en Go se refiere a los números de punto flotante, que son utilizados para representar valores numéricos que pueden tener partes fraccionarias. En Go, se utilizan los tipos `float32` y `float64` para trabajar con números reales.

## Documentación
En Go, los números reales permiten la representación de valores decimales y son esenciales para cálculos matemáticos que requieren precisión en la parte fraccionaria. Existen dos tamaños de números de punto flotante en Go:

- **`float32`**: Un número de punto flotante de 32 bits. Tiene un rango aproximado de 1.4E-45 a 3.4E+38 y una precisión de aproximadamente 7 dígitos decimales.
  
- **`float64`**: Un número de punto flotante de 64 bits. Tiene un rango aproximado de 5.0E-324 a 1.7E+308 y una precisión de aproximadamente 15 dígitos decimales. Este tipo es más comúnmente utilizado debido a su mayor precisión.

### Uso
Para declarar una variable de tipo real en Go, se utiliza la palabra clave `var` seguida del nombre de la variable, el tipo y un valor opcional. Aquí un ejemplo:

```go
var x float64 = 3.14
var y float32 = 2.5
```

Además, Go permite la inferencia de tipos, por lo que se puede declarar una variable sin especificar el tipo:

```go
z := 1.5 // Go infiere que z es de tipo float64
```

## Ejemplos
### Ejemplo 1: Suma de números reales

```go
package main

import "fmt"

func main() {
    a := 2.5
    b := 3.7
    suma := a + b
    fmt.Println("La suma es:", suma) // Salida: La suma es: 6.2
}
```

### Ejemplo 2: Comparación de números reales

```go
package main

import "fmt"

func main() {
    a := 1.1
    b := 1.1
    fmt.Println("a es igual a b:", a == b) // Salida: a es igual a b: true
}
```

## Explicación
Al trabajar con números reales en Go, es importante tener en cuenta ciertos aspectos:

- **Precisión**: Los cálculos con números de punto flotante pueden llevar a resultados inesperados debido a la forma en que los números son representados en la memoria. Por ejemplo, `0.1 + 0.2` no necesariamente dará `0.3` debido a la precisión limitada.

- **Comparaciones**: Al comparar números reales, es recomendable no utilizar la igualdad estricta (`==`) debido a posibles errores de redondeo. En su lugar, se puede comparar si la diferencia entre los números es menor que un pequeño umbral (epsilon).

```go
func sonIguales(a, b float64) bool {
    const epsilon = 1e-9
    return (a-b) < epsilon && (b-a) < epsilon
}
```

## Resumen en una línea
El tipo de dato "real" en Go, representado por `float32` y `float64`, permite realizar cálculos con números de punto flotante, aunque se debe tener cuidado con la precisión en las operaciones.