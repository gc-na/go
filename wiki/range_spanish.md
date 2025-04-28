<!--
Meta Description: # Uso de "range" en Go: Iteración Eficiente sobre Colecciones ## Sinopsis El comando "range" en Go es una poderosa herramienta para iterar sobre difer...
Meta Keywords: range, sobre, fmt, para, iterar
-->

# Uso de "range" en Go: Iteración Eficiente sobre Colecciones

## Sinopsis
El comando "range" en Go es una poderosa herramienta para iterar sobre diferentes estructuras de datos, como arreglos, slices, mapas y canales. Su uso simplifica el proceso de recorrido, permitiendo acceder fácilmente a los elementos y sus índices o claves.

## Documentación
El uso de "range" en Go permite realizar iteraciones sobre diversas colecciones de una manera concisa y legible. Se puede aplicar a:

- **Arreglos y Slices**: Para acceder a los elementos y sus índices.
- **Mapas**: Para acceder a las claves y valores.
- **Canales**: Para recibir valores hasta que el canal se cierre.

### Sintaxis
```go
for index, value := range collection {
    // lógica aquí
}
```

### Propósito
El propósito de "range" es simplificar la iteración, eliminando la necesidad de manejar índices manualmente o usar funciones adicionales para recorrer las colecciones.

### Uso
- **Con arreglos y slices**: 
  ```go
  fruits := []string{"manzana", "banana", "cereza"}
  for index, fruit := range fruits {
      fmt.Println(index, fruit)
  }
  ```

- **Con mapas**:
  ```go
  ages := map[string]int{"Juan": 30, "Ana": 25}
  for name, age := range ages {
      fmt.Println(name, age)
  }
  ```

- **Con canales**:
  ```go
  ch := make(chan int)
  go func() {
      for i := 0; i < 5; i++ {
          ch <- i
      }
      close(ch)
  }()
  
  for num := range ch {
      fmt.Println(num)
  }
  ```

## Ejemplos
### Ejemplo 1: Iterar sobre un Slice
```go
package main

import "fmt"

func main() {
    numbers := []int{1, 2, 3, 4, 5}
    for i, n := range numbers {
        fmt.Printf("Índice: %d, Valor: %d\n", i, n)
    }
}
```

### Ejemplo 2: Iterar sobre un Mapa
```go
package main

import "fmt"

func main() {
    scores := map[string]int{"Matemáticas": 90, "Ciencias": 85}
    for subject, score := range scores {
        fmt.Printf("Materia: %s, Puntuación: %d\n", subject, score)
    }
}
```

## Explicación
Al usar "range", es crucial tener en cuenta lo siguiente:

- **Indices y Claves**: Si no necesitas el índice o la clave, puedes omitirla usando un guion bajo (`_`).
  ```go
  for _, value := range collection {
      // lógica aquí
  }
  ```

- **Manejo de Canales**: Cuando se itera sobre un canal, el bucle se detendrá automáticamente al cerrarse el canal.

- **Mutabilidad**: Al iterar sobre un mapa, si se modifica el mapa durante la iteración, puede causar comportamientos inesperados.

## Resumen en Una Línea
El comando "range" en Go permite iterar de manera efectiva sobre arreglos, slices, mapas y canales, facilitando el acceso a sus elementos y sus índices o claves.