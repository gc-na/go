<!--
Meta Description: # complex128: O Tipo de Dados Complexo em Go ## Sinopse O tipo `complex128` em Go representa números complexos com partes reais e imaginárias de preci...
Meta Keywords: parte, real, números, complexos, complex128
-->

# complex128: O Tipo de Dados Complexo em Go

## Sinopse
O tipo `complex128` em Go representa números complexos com partes reais e imaginárias de precisão dupla, permitindo operações matemáticas avançadas em programas que necessitam de cálculos complexos.

## Documentação
O `complex128` é um dos tipos de dados primitivos em Go, que utiliza 128 bits para armazenar números complexos. Um número complexo é composto por uma parte real e uma parte imaginária, ambas representadas como números de ponto flutuante de precisão dupla (`float64`). O tipo `complex128` é frequentemente utilizado em aplicações que envolvem matemática avançada, processamento de sinais e gráficos.

### Propósito
O `complex128` permite que os desenvolvedores realizem operações matemáticas em números complexos de forma simples e eficiente, utilizando operadores aritméticos padrão.

### Uso
Para declarar uma variável do tipo `complex128`, você pode utilizar a função `complex()`, que aceita duas partes: a parte real e a parte imaginária. A sintaxe é a seguinte:

```go
var c complex128 = complex(real, imag)
```

### Detalhes
- A parte real e a parte imaginária são do tipo `float64`.
- Você pode utilizar operadores como `+`, `-`, `*`, e `/` para realizar operações aritméticas com números complexos.
- A função `real()` retorna a parte real de um número complexo, enquanto `imag()` retorna a parte imaginária.

## Exemplos
### Exemplo 1: Criação de um número complexo
```go
package main

import (
    "fmt"
)

func main() {
    c := complex(3.0, 4.0) // número complexo 3 + 4i
    fmt.Println(c)         // Saída: (3+4i)
}
```

### Exemplo 2: Operações com números complexos
```go
package main

import (
    "fmt"
)

func main() {
    a := complex(1.0, 2.0)
    b := complex(3.0, 4.0)

    soma := a + b
    fmt.Println("Soma:", soma) // Saída: Soma: (4+6i)

    produto := a * b
    fmt.Println("Produto:", produto) // Saída: Produto: (-5+10i)
}
```

### Exemplo 3: Extraindo partes real e imaginária
```go
package main

import (
    "fmt"
)

func main() {
    c := complex(5.0, 12.0)
    fmt.Println("Parte real:", real(c))   // Saída: Parte real: 5
    fmt.Println("Parte imaginária:", imag(c)) // Saída: Parte imaginária: 12
}
```

## Explicação
Ao trabalhar com o tipo `complex128`, é importante lembrar que:
- Os números complexos não possuem uma representação visual direta, portanto, ao imprimir, eles aparecerão no formato `(real+imaginaryi)`.
- O uso de operadores aritméticos pode ser confuso se não estiver familiarizado com as regras da aritmética de números complexos.
- Não deve-se tentar realizar comparações diretas entre números complexos usando operadores como `==` ou `!=`, pois isso não é suportado em Go.

## Resumo em uma linha
O `complex128` em Go é um tipo de dado que representa números complexos de precisão dupla, permitindo operações matemáticas eficientes e simples.