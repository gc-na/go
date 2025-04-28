<!--
Meta Description: # Uso de la función `append` en Go: Cómo agregar elementos a un slice ## Sinopsis La función `append` en Go es una herramienta fundamental para agrega...
Meta Keywords: slice, append, elementos, que, agregar
-->

# Uso de la función `append` en Go: Cómo agregar elementos a un slice

## Sinopsis
La función `append` en Go es una herramienta fundamental para agregar elementos a un slice, permitiendo la manipulación dinámica de colecciones de datos. Esta función es esencial para el desarrollo eficiente en Go, ya que optimiza el manejo de memoria y la extensión de estructuras de datos.

## Documentación
### Propósito
La función `append` se utiliza para añadir uno o más elementos a un slice en Go. Esta función no solo agrega elementos, sino que también maneja la capacidad del slice, creando un nuevo slice si es necesario.

### Uso
La sintaxis básica de `append` es la siguiente:

```go
slice = append(slice, elementos...)
```

- `slice`: El slice al que se le agregarán nuevos elementos.
- `elementos`: Uno o más elementos que se desean agregar al slice. Se puede utilizar el operador de expansión (`...`) para agregar múltiples elementos a la vez.

### Detalles
- Si la capacidad del slice original es suficiente para acomodar los nuevos elementos, `append` simplemente agrega los elementos y devuelve el mismo slice.
- Si no hay suficiente capacidad, `append` crea un nuevo slice, copia los elementos existentes y añade los nuevos.
- El retorno de `append` es importante, ya que el slice original puede cambiar si se excede su capacidad.

## Ejemplos

### Ejemplo 1: Agregar un solo elemento
```go
package main

import "fmt"

func main() {
    numeros := []int{1, 2, 3}
    numeros = append(numeros, 4)
    fmt.Println(numeros) // Salida: [1 2 3 4]
}
```

### Ejemplo 2: Agregar múltiples elementos
```go
package main

import "fmt"

func main() {
    letras := []string{"a", "b", "c"}
    letras = append(letras, "d", "e", "f")
    fmt.Println(letras) // Salida: [a b c d e f]
}
```

### Ejemplo 3: Usar el operador de expansión
```go
package main

import "fmt"

func main() {
    frutas := []string{"manzana", "banana"}
    nuevasFrutas := []string{"naranja", "kiwi"}
    frutas = append(frutas, nuevasFrutas...)
    fmt.Println(frutas) // Salida: [manzana banana naranja kiwi]
}
```

## Explicación
Una trampa común al usar `append` es olvidar que podría devolver un nuevo slice, lo que significa que es necesario asignar el resultado de `append` a la variable original. Además, si se utiliza `append` repetidamente en un bucle, es recomendable verificar la capacidad del slice para evitar copias innecesarias y optimizar el rendimiento.

Otra consideración es que `append` puede tener un comportamiento inesperado si se trabaja con punteros a slices, ya que modificar el slice original después de un `append` puede no reflejarse en las variables que apuntan a su dirección.

## Resumen en una línea
La función `append` en Go es clave para agregar elementos a un slice, manejando dinámicamente la memoria y aumentando su capacidad según sea necesario.