<!--
Meta Description: # Uso de "var" en Go: Declaración de Variables ## Sinopsis El comando `var` en Go se utiliza para declarar variables. Permite definir el tipo de datos...
Meta Keywords: var, variables, main, fmt, declaración
-->

# Uso de "var" en Go: Declaración de Variables

## Sinopsis
El comando `var` en Go se utiliza para declarar variables. Permite definir el tipo de datos y la visibilidad de la variable, siendo una parte fundamental en la gestión de datos en cualquier programa escrito en este lenguaje.

## Documentación
En Go, la declaración de variables se puede realizar de varias maneras. La forma más común es mediante el uso de la palabra clave `var`, seguida del nombre de la variable, el tipo de datos y, opcionalmente, un valor inicial.

### Sintaxis
```go
var nombreVariable tipoDeDato
```

### Ejemplo con valor inicial
```go
var edad int = 30
```

### Declaración múltiple
También se pueden declarar múltiples variables en una sola línea:
```go
var a, b, c int
```

### Declaración sin tipo
Si se proporciona un valor inicial, el tipo se infiere automáticamente:
```go
var nombre = "Juan"
```

### Alcance de las variables
Las variables declaradas con `var` tienen un alcance que puede ser local (dentro de una función) o global (fuera de cualquier función).

## Ejemplos

### Ejemplo 1: Declaración Simple
```go
package main

import "fmt"

func main() {
    var mensaje string = "Hola, mundo!"
    fmt.Println(mensaje)
}
```

### Ejemplo 2: Declaración Múltiple
```go
package main

import "fmt"

func main() {
    var a, b int = 5, 10
    fmt.Println(a + b)
}
```

### Ejemplo 3: Inferencia de Tipo
```go
package main

import "fmt"

func main() {
    var pi = 3.14 // tipo inferido como float64
    fmt.Println(pi)
}
```

### Ejemplo 4: Alcance Global
```go
package main

import "fmt"

var pais = "España" // Variable global

func main() {
    fmt.Println(pais)
}
```

## Explicación
Al usar `var`, es importante tener en cuenta que:
- Las variables no inicializadas tendrán valor cero según su tipo (0 para enteros, "" para cadenas, etc.).
- Las variables globales pueden ser accesibles desde cualquier función, mientras que las locales solo son visibles dentro de su bloque.
- Si se intenta usar una variable no declarada, se generará un error de compilación.
- Go fomenta el uso de la declaración corta `:=` para variables locales, lo cual es más conveniente, pero `var` sigue siendo útil para declaraciones más explícitas y para variables globales.

## Resumen en una frase
La palabra clave `var` en Go permite declarar variables con tipos de datos definidos, facilitando la gestión y el almacenamiento de información en programas.