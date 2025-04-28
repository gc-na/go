<!--
Meta Description: # Map em Go: Estruturas de Dados Eficientes ## Sinopse O `map` em Go é uma estrutura de dados que permite armazenar pares de chave-valor de forma efic...
Meta Keywords: chave, map, valor, uma, idade
-->

# Map em Go: Estruturas de Dados Eficientes

## Sinopse
O `map` em Go é uma estrutura de dados que permite armazenar pares de chave-valor de forma eficiente, facilitando a busca, inserção e exclusão de elementos.

## Documentação
O `map` é uma coleção não ordenada de pares de chave e valor. Ele é uma das estruturas de dados mais utilizadas na linguagem Go, permitindo que os desenvolvedores mantenham dados organizados e acessem informações rapidamente através de uma chave única.

### Propósito
O principal objetivo do `map` é fornecer uma maneira rápida e fácil de associar dados, permitindo um acesso eficiente baseado em chaves.

### Uso
Para declarar um `map`, utiliza-se a seguinte sintaxe:
```go
m := make(map[chaveTipo]valorTipo)
```
Ou, de forma literal:
```go
m := map[chaveTipo]valorTipo{
    chave1: valor1,
    chave2: valor2,
}
```

### Detalhes
- **Chave e Valor**: As chaves devem ser de um tipo que seja comparável (por exemplo, strings, inteiros, etc.), enquanto os valores podem ser de qualquer tipo.
- **Acesso**: Para acessar um valor, usa-se a chave correspondente:
  ```go
  valor := m[chave]
  ```
- **Inserção e Atualização**: Para adicionar ou atualizar um valor, basta atribuí-lo à chave:
  ```go
  m[chave] = novoValor
  ```
- **Exclusão**: Para remover um elemento, utiliza-se a função `delete`:
  ```go
  delete(m, chave)
  ```

## Exemplos

### Exemplo Básico de Criação e Uso
```go
package main

import (
    "fmt"
)

func main() {
    // Criação de um mapa
    idade := make(map[string]int)

    // Adicionando elementos
    idade["Alice"] = 30
    idade["Bob"] = 25

    // Acessando elementos
    fmt.Println("Idade de Alice:", idade["Alice"])

    // Removendo um elemento
    delete(idade, "Bob")
    fmt.Println("Idade de Bob:", idade["Bob"]) // Imprime 0, pois Bob foi removido
}
```

### Exemplo com Inicialização Direta
```go
package main

import (
    "fmt"
)

func main() {
    // Inicialização direta
    frutas := map[string]int{
        "maçã":  10,
        "banana": 5,
        "laranja": 8,
    }

    // Iterando sobre o mapa
    for fruta, quantidade := range frutas {
        fmt.Printf("%s: %d\n", fruta, quantidade)
    }
}
```

## Explicação
Embora os `maps` sejam extremamente úteis, existem algumas armadilhas comuns:

- **Chaves não comparáveis**: Tipos como slices e mapas não podem ser usados como chaves.
- **Acesso a chaves não existentes**: Quando se tenta acessar uma chave que não existe, Go retorna o valor zero do tipo do valor armazenado no mapa, o que pode ser confuso.
- **Concorrência**: `maps` não são seguros para acesso concorrente. Se múltiplas goroutines acessarem e modificarem um mapa simultaneamente, é necessário usar mecanismos de sincronização como `sync.Mutex`.

## Resumo em Uma Linha
O `map` em Go é uma estrutura de dados que permite armazenar pares de chave-valor, oferecendo acesso rápido e eficiente a dados associados.