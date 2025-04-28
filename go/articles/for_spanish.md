<!--
Meta Description: # Uso del Bucle "for" en Go: Guía Completa ## Sinopsis El bucle "for" en Go es una herramienta fundamental para la iteración sobre colecciones y ejecu...
Meta Keywords: bucle, fmt, una, main, sobre
-->

# Uso del Bucle "for" en Go: Guía Completa

## Sinopsis
El bucle "for" en Go es una herramienta fundamental para la iteración sobre colecciones y ejecución repetitiva de código. Este comando se destaca por su simplicidad y versatilidad, permitiendo diversas formas de bucles.

## Documentación
El bucle "for" es la única estructura de control de bucle en Go, lo que simplifica la sintaxis y la comprensión. Puede utilizarse de varias maneras:

1. **Bucle tradicional**: Similar a otros lenguajes, se puede definir con una inicialización, condición y post-incremento.
   ```go
   for i := 0; i < 10; i++ {
       fmt.Println(i)
   }
   ```

2. **Bucle mientras**: Al omitir la inicialización y el post-incremento, el bucle se comporta como un bucle "while".
   ```go
   i := 0
   for i < 10 {
       fmt.Println(i)
       i++
   }
   ```

3. **Bucle infinito**: Si se omite la condición, se crea un bucle infinito. Es fundamental usar una instrucción de ruptura para evitar que el programa se quede atascado.
   ```go
   for {
       fmt.Println("Este bucle es infinito")
       break // Se debe incluir una forma de salir del bucle
   }
   ```

4. **Iteración sobre colecciones**: Se puede usar `range` para iterar sobre arrays, slices, maps y canales.
   ```go
   mySlice := []int{1, 2, 3}
   for index, value := range mySlice {
       fmt.Printf("Índice: %d, Valor: %d\n", index, value)
   }
   ```

## Ejemplos
### Ejemplo 1: Bucle tradicional
```go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println("Número:", i)
    }
}
```
### Ejemplo 2: Bucle mientras
```go
package main

import "fmt"

func main() {
    j := 0
    for j < 5 {
        fmt.Println("Número:", j)
        j++
    }
}
```
### Ejemplo 3: Iterando sobre un mapa
```go
package main

import "fmt"

func main() {
    myMap := map[string]int{"uno": 1, "dos": 2}
    for key, value := range myMap {
        fmt.Printf("Clave: %s, Valor: %d\n", key, value)
    }
}
```

## Explicación
El uso del bucle "for" es sencillo, pero hay algunos puntos importantes a considerar:

- **Bucle infinito**: Asegúrate de incluir una condición de salida si usas un bucle infinito. De lo contrario, tu programa se bloqueará.
- **Variable de control**: La variable de control debe ser inicializada correctamente para evitar comportamientos inesperados.
- **Uso de `break` y `continue`**: Puedes interrumpir un bucle con `break` o saltar a la siguiente iteración con `continue`.

## Resumen en una línea
El bucle "for" en Go es una estructura de control versátil que permite iterar de manera eficiente sobre colecciones y ejecutar código repetidamente.