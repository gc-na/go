<!--
Meta Description: # Comando "append" em Go: Como Adicionar Elementos a Slices ## Sinopse O comando `append` em Go é uma função essencial que permite adicionar novos ele...
Meta Keywords: append, elementos, slice, nums, que
-->

# Comando "append" em Go: Como Adicionar Elementos a Slices

## Sinopse
O comando `append` em Go é uma função essencial que permite adicionar novos elementos a slices de forma eficiente, aumentando a capacidade de armazenamento conforme necessário.

## Documentação

### Propósito
A função `append` é utilizada para adicionar elementos a um slice já existente. Ela é uma das principais formas de manipulação de dados em Go, permitindo que os desenvolvedores aumentem dinamicamente os slices sem a necessidade de gerenciamento manual da memória.

### Uso
A sintaxe básica da função `append` é:
```go
slice = append(slice, elementos...)
```
Onde `slice` é o slice existente e `elementos` são os novos itens que você deseja adicionar. O operador `...` é utilizado para descompactar uma lista de elementos se você estiver adicionando mais de um de uma vez.

### Detalhes
- A função `append` retorna um novo slice, que pode ter uma capacidade maior do que o slice original, caso o espaço atual seja insuficiente.
- É importante lembrar que `append` não modifica o slice original, mas sim retorna um novo slice que deve ser atribuído a uma variável.
- `append` pode ser utilizado para adicionar elementos de qualquer tipo que suporte a operação, incluindo tipos primitivos e structs.

## Exemplos

### Exemplo 1: Adicionando um Único Elemento
```go
package main

import "fmt"

func main() {
    var nums []int
    nums = append(nums, 1)
    fmt.Println(nums) // Saída: [1]
}
```

### Exemplo 2: Adicionando Vários Elementos
```go
package main

import "fmt"

func main() {
    nums := []int{1, 2, 3}
    nums = append(nums, 4, 5, 6)
    fmt.Println(nums) // Saída: [1 2 3 4 5 6]
}
```

### Exemplo 3: Adicionando Elementos de Outro Slice
```go
package main

import "fmt"

func main() {
    nums1 := []int{1, 2, 3}
    nums2 := []int{4, 5, 6}
    nums1 = append(nums1, nums2...) // Descompactando nums2
    fmt.Println(nums1) // Saída: [1 2 3 4 5 6]
}
```

## Explicação
Um dos erros comuns ao usar `append` é não atribuir o resultado de volta ao slice. Por exemplo:
```go
package main

import "fmt"

func main() {
    nums := []int{1, 2, 3}
    append(nums, 4) // Isso não modifica 'nums'
    fmt.Println(nums) // Saída: [1 2 3]
}
```
Além disso, é importante ter em mente que, se um slice atinge sua capacidade máxima e novos elementos são adicionados, Go automaticamente aloca um novo array e copia os elementos existentes, o que pode impactar a performance em operações intensivas.

## Resumo em Uma Linha
A função `append` em Go permite adicionar elementos a slices de maneira eficiente, retornando um novo slice com os elementos incluídos.