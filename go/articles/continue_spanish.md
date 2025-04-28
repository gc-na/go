<!--
Meta Description: # La sentencia "continue" en Go: Controlando el Flujo de Bucles ## Sinopsis La sentencia `continue` en Go se utiliza dentro de bucles para omitir la i...
Meta Keywords: continue, bucle, para, sentencia, bucles
-->

# La sentencia "continue" en Go: Controlando el Flujo de Bucles

## Sinopsis
La sentencia `continue` en Go se utiliza dentro de bucles para omitir la iteración actual y pasar directamente a la siguiente. Es una herramienta útil para controlar el flujo de ejecución en estructuras de repetición como `for`.

## Documentación
La sentencia `continue` se emplea en bucles `for` y permite que el programa ignore el resto del código en la iteración actual y vuelva al inicio del bucle para evaluar la condición nuevamente. Es especialmente útil cuando se desea saltar ciertas condiciones sin finalizar el bucle por completo.

### Uso
La sintaxis básica de la sentencia `continue` es la siguiente:

```go
continue
```

Esta sentencia puede aparecer en cualquier lugar dentro de un bucle, y su uso es común en situaciones donde se quiere evitar la ejecución de ciertas instrucciones bajo condiciones específicas. 

### Detalles
- **Ubicación**: `continue` puede ser utilizado en cualquier bucle `for`, incluyendo bucles anidados.
- **Alcance**: Al utilizar `continue`, solo se afecta el bucle más interno en el que se encuentra la sentencia.
- **Condiciones**: Es común utilizar `continue` junto con declaraciones condicionales (`if`) para determinar cuándo omitir la iteración.

## Ejemplos

### Ejemplo Básico
En el siguiente ejemplo, se utiliza `continue` para saltar los números impares en un bucle:

```go
package main

import "fmt"

func main() {
    for i := 1; i <= 10; i++ {
        if i%2 != 0 {
            continue
        }
        fmt.Println(i)
    }
}
```
*Salida:*
```
2
4
6
8
10
```

### Ejemplo con Bucles Anidados
En este ejemplo, se utiliza `continue` en un bucle anidado para omitir la impresión de ciertos números:

```go
package main

import "fmt"

func main() {
    for i := 1; i <= 3; i++ {
        for j := 1; j <= 3; j++ {
            if j == 2 {
                continue
            }
            fmt.Printf("i: %d, j: %d\n", i, j)
        }
    }
}
```
*Salida:*
```
i: 1, j: 1
i: 1, j: 3
i: 2, j: 1
i: 2, j: 3
i: 3, j: 1
i: 3, j: 3
```

## Explicación
Uno de los errores comunes al usar `continue` es olvidarse de la condición que controla cuándo se debe omitir la iteración. Si no se establece correctamente, se podría saltar más iteraciones de las deseadas o incluso crear un bucle infinito.

Es importante recordar que `continue` solo afecta a la iteración actual del bucle, lo que significa que no se puede usar para salir completamente de múltiples niveles de bucles. Para eso, se debe utilizar `break`.

## Resumen en una línea
La sentencia `continue` en Go permite omitir la iteración actual de un bucle y continuar con la siguiente, facilitando así el control del flujo de ejecución.