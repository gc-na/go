<!--
Meta Description: # Copia en Go: Uso y Ejemplos de la Función `copy` ## Sinopsis La función `copy` en Go permite copiar elementos de un slice a otro, proporcionando una...
Meta Keywords: slice, copy, elementos, destino, que
-->

# Copia en Go: Uso y Ejemplos de la Función `copy`

## Sinopsis
La función `copy` en Go permite copiar elementos de un slice a otro, proporcionando una forma eficiente de manejar datos en memoria. Es especialmente útil para la manipulación de estructuras de datos y la gestión de arreglos.

## Documentación
La función `copy` en Go tiene la siguiente firma:

```go
func copy(dst, src []Type) int
```

### Propósito
La función `copy` se utiliza para copiar elementos de un slice fuente (`src`) a un slice destino (`dst`). El número de elementos copiados es el mínimo entre la longitud del slice origen y el tamaño del slice destino.

### Uso
- **Parámetros**:
  - `dst`: El slice destino donde se copiarán los elementos.
  - `src`: El slice fuente desde el cual se copiarán los elementos.
- **Valor de retorno**: Devuelve un entero que representa la cantidad de elementos que fueron copiados.

### Detalles
- Si el slice destino es más pequeño que el slice fuente, solo se copiarán los elementos que quepan en el destino.
- Si el slice destino es más grande, solo se copiarán los elementos que existan en el slice fuente, y el resto del destino permanecerá sin cambios.
- La función `copy` realiza una copia superficial, lo que significa que si los elementos son tipos de referencia (como slices o mapas), se copiarán las referencias, no los valores.

## Ejemplos

### Ejemplo Básico de Uso

```go
package main

import "fmt"

func main() {
    src := []int{1, 2, 3, 4, 5}
    dst := make([]int, 3)

    n := copy(dst, src)
    fmt.Println(dst) // Salida: [1 2 3]
    fmt.Println(n)   // Salida: 3
}
```

### Copia con Destino Más Grande

```go
package main

import "fmt"

func main() {
    src := []string{"a", "b", "c"}
    dst := make([]string, 5)

    n := copy(dst, src)
    fmt.Println(dst) // Salida: [a b c ]
    fmt.Println(n)   // Salida: 3
}
```

## Explicación
Al utilizar la función `copy`, es importante tener en cuenta lo siguiente:

- **Longitud de los Slices**: Asegúrate de que el slice destino tenga suficiente longitud para los elementos que deseas copiar. Si no, solo se copian los elementos que caben.
- **Tipos de Datos**: La función `copy` es genérica y puede usarse con cualquier tipo de datos, pero ten en cuenta que la copia es superficial para tipos de referencia.
- **Nil Slices**: Si el slice destino es `nil`, no se producirá un pánico, pero tampoco se copiará nada. Asegúrate de inicializar el slice destino antes de usar `copy`.

## Resumen en Una Línea
La función `copy` en Go permite copiar eficientemente elementos de un slice a otro, gestionando la longitud de los slices de manera efectiva.