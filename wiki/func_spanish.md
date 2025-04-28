<!--
Meta Description: # Funciones en Go: Comprendiendo `func` ## Sinopsis La declaración `func` en Go se utiliza para definir funciones, que son bloques de código reutiliza...
Meta Keywords: funciones, func, función, una, suma
-->

# Funciones en Go: Comprendiendo `func`

## Sinopsis
La declaración `func` en Go se utiliza para definir funciones, que son bloques de código reutilizables que realizan tareas específicas. Las funciones son un pilar fundamental en la programación en Go, permitiendo una estructura clara y modular en el código.

## Documentación
En Go, la palabra clave `func` se utiliza para declarar funciones. Una función puede tomar cero o más parámetros y puede devolver cero o más valores. La sintaxis general para declarar una función es la siguiente:

```go
func NombreFuncion(parametros) (tiposDeRetorno) {
    // cuerpo de la función
}
```

### Propósito
El propósito de `func` es encapsular un conjunto de operaciones que se pueden ejecutar de manera independiente y reutilizable. Las funciones mejoran la legibilidad y mantienen el código organizado.

### Uso
Para declarar una función, se utiliza la palabra clave `func`, seguida del nombre de la función, los parámetros entre paréntesis y el tipo de retorno. Por ejemplo:

```go
func Sumar(a int, b int) int {
    return a + b
}
```

En este caso, `Sumar` toma dos enteros como parámetros y devuelve su suma como un entero.

### Detalles
- **Parámetros**: Se pueden definir múltiples parámetros separados por comas. Cada parámetro debe tener un tipo especificado.
- **Valores de retorno**: Una función puede devolver múltiples valores, que se especifican como una lista entre paréntesis.
- **Funciones anónimas**: Go también permite la creación de funciones sin nombre, que se pueden asignar a variables o pasar como argumentos.

## Ejemplos

### Ejemplo 1: Función básica
```go
package main

import "fmt"

func Saludar(nombre string) string {
    return "Hola " + nombre
}

func main() {
    mensaje := Saludar("Juan")
    fmt.Println(mensaje)  // Salida: Hola Juan
}
```

### Ejemplo 2: Función con múltiples valores de retorno
```go
package main

import "fmt"

func Operaciones(a, b int) (int, int) {
    suma := a + b
    resta := a - b
    return suma, resta
}

func main() {
    suma, resta := Operaciones(10, 5)
    fmt.Println("Suma:", suma, "Resta:", resta)  // Salida: Suma: 15 Resta: 5
}
```

## Explicación
Al trabajar con funciones en Go, es importante tener en cuenta lo siguiente:

- **Alcance de las variables**: Las variables definidas dentro de una función no son accesibles fuera de ella. Esto ayuda a evitar conflictos de nombres y mejora la encapsulación.
- **Funciones como valores**: Puedes asignar funciones a variables o pasarlas como argumentos a otras funciones. Esto es útil para implementar callbacks y funciones de orden superior.
- **Errores comunes**: Un error común al declarar funciones es no especificar correctamente el tipo de retorno, lo que puede causar confusión y errores en tiempo de compilación.

## Resumen en una línea
La declaración `func` en Go permite crear funciones reutilizables, mejorando la modularidad y la organización del código.