<!--
Meta Description: # Map en Go: Todo lo que Necesitas Saber ## Sinopsis Los mapas en Go son estructuras de datos que permiten almacenar pares de clave-valor, proporciona...
Meta Keywords: clave, valor, mapa, para, que
-->

# Map en Go: Todo lo que Necesitas Saber

## Sinopsis
Los mapas en Go son estructuras de datos que permiten almacenar pares de clave-valor, proporcionando una forma eficiente de acceder a datos a través de una clave única. Son similares a los diccionarios en otros lenguajes de programación.

## Documentación
En Go, un mapa es una colección desordenada de elementos, donde cada elemento consta de una clave única y un valor asociado. Los mapas son muy útiles para situaciones donde necesitas asociar datos de manera rápida y eficiente.

### Propósito
Los mapas son utilizados principalmente para:
- Almacenar relaciones entre claves y valores.
- Permitir búsquedas rápidas de datos.
- Manejar colecciones de datos no ordenadas.

### Uso
Para declarar un mapa en Go, se utiliza la sintaxis `make` o la declaración de tipo. La declaración de un mapa se realiza de la siguiente manera:

```go
var m map[string]int // Declara un mapa que asocia strings a integers
```

O utilizando `make`:

```go
m := make(map[string]int) // Crear un mapa vacío
```

Para agregar o actualizar un elemento en el mapa, se utiliza la siguiente sintaxis:

```go
m["clave"] = valor // Asigna un valor a una clave
```

Para obtener un valor, simplemente se accede a la clave:

```go
valor := m["clave"] // Obtiene el valor asociado a "clave"
```

Si intentas acceder a una clave que no existe, Go devolverá el valor cero del tipo de datos, en este caso, 0 para `int`.

### Detalles
Los mapas en Go son:
- **No ordenados**: La iteración sobre un mapa no garantiza ningún orden.
- **Mutable**: Puedes agregar, eliminar y modificar elementos en un mapa.
- **Concurrentes**: No son seguros para el uso concurrente sin sincronización.

## Ejemplos

### Ejemplo Básico de Creación y Uso de un Mapa
```go
package main

import "fmt"

func main() {
    // Crear un mapa
    m := make(map[string]int)

    // Agregar elementos
    m["uno"] = 1
    m["dos"] = 2

    // Acceder a elementos
    fmt.Println(m["uno"]) // Salida: 1

    // Modificar un elemento
    m["uno"] = 11
    fmt.Println(m["uno"]) // Salida: 11

    // Eliminar un elemento
    delete(m, "dos")
    fmt.Println(m["dos"]) // Salida: 0 (valor cero para int)
}
```

### Ejemplo de Iteración sobre un Mapa
```go
package main

import "fmt"

func main() {
    m := map[string]int{"uno": 1, "dos": 2, "tres": 3}

    // Iterar sobre el mapa
    for clave, valor := range m {
        fmt.Printf("Clave: %s, Valor: %d\n", clave, valor)
    }
}
```

## Explicación
Al trabajar con mapas en Go, es importante tener en cuenta que:
- Las claves en un mapa deben ser de un tipo que sea comparable (por ejemplo, no puedes usar slices como claves).
- Los mapas no son seguros para el uso concurrente. Si necesitas acceder a un mapa desde múltiples goroutines, deberías utilizar un mecanismo de sincronización como `sync.Mutex`.
- Intentar acceder a una clave que no existe no genera un error, pero devolverá el valor cero del tipo correspondiente.

## Resumen en Una Línea
Los mapas en Go son estructuras de datos que permiten almacenar y acceder a pares de clave-valor de manera eficiente y desordenada.