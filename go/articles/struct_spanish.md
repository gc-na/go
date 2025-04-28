<!--
Meta Description: # Estructuras en Go: Todo lo que Necesitas Saber ## Sinopsis Las estructuras en Go son tipos de datos compuestos que permiten agrupar valores relacion...
Meta Keywords: una, estructuras, estructura, que, nombre
-->

# Estructuras en Go: Todo lo que Necesitas Saber

## Sinopsis
Las estructuras en Go son tipos de datos compuestos que permiten agrupar valores relacionados bajo un mismo nombre. Son fundamentales para la programación orientada a objetos en Go, facilitando la organización y manejo de datos complejos.

## Documentación
Las estructuras, o `structs`, en Go se utilizan para definir tipos de datos personalizados que pueden contener múltiples campos, cada uno de los cuales puede tener un tipo diferente. Esto permite crear modelos que reflejan la complejidad de las entidades en el mundo real.

### Definición de una Estructura
Para definir una estructura en Go, se utiliza la palabra clave `type`, seguida del nombre de la estructura y la palabra clave `struct`. Por ejemplo:

```go
type Persona struct {
    Nombre string
    Edad   int
}
```

### Creación de una Instancia
Una vez definida la estructura, se puede crear una instancia de la misma de la siguiente manera:

```go
persona1 := Persona{
    Nombre: "Juan",
    Edad:   30,
}
```

### Acceso a los Campos
Los campos de una estructura se acceden utilizando el operador de punto (`.`):

```go
fmt.Println(persona1.Nombre) // Salida: Juan
```

### Métodos en Estructuras
Go permite asociar métodos a estructuras. Esto se hace definiendo una función con un receptor, que puede ser un puntero o un valor de la estructura:

```go
func (p Persona) Saludar() {
    fmt.Printf("Hola, mi nombre es %s y tengo %d años.\n", p.Nombre, p.Edad)
}
```

## Ejemplos
**Ejemplo 1: Definición y uso básico de una estructura**

```go
package main

import "fmt"

type Coche struct {
    Marca  string
    Modelo string
    Año    int
}

func main() {
    coche1 := Coche{"Toyota", "Corolla", 2020}
    fmt.Println(coche1.Marca) // Salida: Toyota
}
```

**Ejemplo 2: Métodos en estructuras**

```go
type Circulo struct {
    Radio float64
}

func (c Circulo) Area() float64 {
    return 3.14 * c.Radio * c.Radio
}

func main() {
    circulo1 := Circulo{5}
    fmt.Println(circulo1.Area()) // Salida: 78.5
}
```

## Explicación
Al trabajar con estructuras, es importante tener en cuenta algunos aspectos:

- **Punteros vs. Valores**: Al pasar una estructura como argumento a una función, se puede pasar por valor (copia de la estructura) o por puntero (referencia a la estructura original). Pasar por puntero es más eficiente para estructuras grandes.

- **Campos Anidados**: Las estructuras pueden contener otras estructuras, lo que permite crear jerarquías complejas. Por ejemplo:

    ```go
    type Dirección struct {
        Calle, Ciudad string
    }

    type Usuario struct {
        Nombre    string
        Dirección Dirección
    }
    ```

- **Exportación de Campos**: Para que un campo de una estructura sea accesible fuera del paquete donde se define, debe comenzar con una letra mayúscula.

## Resumen en una Línea
Las estructuras en Go son tipos de datos que agrupan múltiples valores, permitiendo una mejor organización y modelado de datos complejos.