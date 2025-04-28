<!--
Meta Description: # len em Go: Entenda a Função para Obter o Tamanho de Estruturas ## Sinopse A função `len` em Go é utilizada para retornar o número de elementos em um...
Meta Keywords: len, número, para, função, retorna
-->

# len em Go: Entenda a Função para Obter o Tamanho de Estruturas

## Sinopse
A função `len` em Go é utilizada para retornar o número de elementos em uma coleção, como arrays, slices, maps e strings. Essa função é fundamental para manipulações de dados e controle de estruturas dentro da linguagem.

## Documentação
A função `len` é uma função embutida em Go que fornece a contagem de elementos de diferentes tipos de coleções. A sintaxe básica para utilizá-la é:

```go
len(v interface{}) int
```

### Propósito
O propósito da função `len` é fornecer uma maneira eficiente e direta de obter o tamanho de diferentes tipos de dados, o que é essencial para iterações, validações e operações de controle de fluxo.

### Uso
Você pode usar `len` em:

- **Arrays**: Retorna o número de elementos no array.
- **Slices**: Retorna o número de elementos no slice.
- **Maps**: Retorna o número de pares chave-valor no map.
- **Strings**: Retorna o número de bytes na string.

### Detalhes
- Para arrays e slices, `len` retorna o número de elementos, enquanto para strings, retorna o número de bytes (não caracteres).
- Para maps, `len` retorna a quantidade de entradas, que pode ser útil para verificar se um map está vazio.

## Exemplos

### Exemplo 1: Usando len com um Slice
```go
package main

import "fmt"

func main() {
    slice := []int{1, 2, 3, 4, 5}
    fmt.Println(len(slice)) // Saída: 5
}
```

### Exemplo 2: Usando len com um Array
```go
package main

import "fmt"

func main() {
    array := [3]int{10, 20, 30}
    fmt.Println(len(array)) // Saída: 3
}
```

### Exemplo 3: Usando len com um Map
```go
package main

import "fmt"

func main() {
    m := map[string]int{"a": 1, "b": 2}
    fmt.Println(len(m)) // Saída: 2
}
```

### Exemplo 4: Usando len com uma String
```go
package main

import "fmt"

func main() {
    str := "Olá, Mundo!"
    fmt.Println(len(str)) // Saída: 13
}
```

## Explicação
Embora a função `len` seja simples de usar, é importante ter atenção a alguns detalhes:

- **Strings**: O retorno de `len` para strings é o número de bytes, não o número de caracteres. Em strings com caracteres Unicode, isso pode resultar em contagens inesperadas.
- **Slices e Arrays**: Ao trabalhar com slices, lembre-se de que o comprimento pode mudar se você adicionar ou remover elementos.
- **Maps**: Um map vazio retornará 0. Portanto, é comum verificar se um map está vazio com `len(m) == 0`.

## Resumo em Uma Linha
A função `len` em Go retorna o número de elementos em arrays, slices, maps e o número de bytes em strings.