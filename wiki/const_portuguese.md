<!--
Meta Description: # Constantes em Go: Compreendendo o Uso de "const" ## Sinopse O comando "const" em Go permite a definição de constantes, que são valores fixos que não...
Meta Keywords: constantes, const, que, não, ser
-->

# Constantes em Go: Compreendendo o Uso de "const"

## Sinopse
O comando "const" em Go permite a definição de constantes, que são valores fixos que não podem ser alterados durante a execução do programa. As constantes são tipicamente utilizadas para representar valores que não mudam, como limites, configurações e chaves.

## Documentação
No Go, a palavra-chave `const` é usada para declarar constantes, que são identificadores que possuem um valor fixo. As constantes podem ser de tipos básicos, como inteiros, floats, strings e booleanos.

### Propósito
As constantes são úteis para:
- Melhorar a legibilidade do código, nomeando valores que seriam difíceis de entender se fossem apenas números ou strings.
- Prevenir erros de alteração acidental de valores que não devem mudar.
- Facilitar a manutenção do código, permitindo que valores sejam atualizados em um único local.

### Uso
A declaração de uma constante é feita da seguinte forma:

```go
const nomeDaConstante tipo = valor
```

Exemplo de declaração de constantes:

```go
const pi float64 = 3.14
const nome string = "Go"
const ativo bool = true
```

O Go também permite a declaração de várias constantes em uma única linha, utilizando parênteses:

```go
const (
    a = 1
    b = 2
    c = 3
)
```

### Detalhes
- As constantes podem ser usadas em expressões aritméticas, mas não podem ser alteradas após a definição.
- O Go suporta a inferência de tipos, permitindo que você declare uma constante sem especificar seu tipo. O tipo será inferido com base no valor atribuído.

```go
const temperatura = 37.5 // tipo inferido como float64
```

## Exemplos
Aqui estão alguns exemplos simples de como usar constantes em Go:

### Exemplo 1: Declaração de uma constante simples
```go
package main

import "fmt"

const pi = 3.14

func main() {
    fmt.Println("O valor de pi é:", pi)
}
```

### Exemplo 2: Usando constantes em expressões
```go
package main

import "fmt"

const (
    largura = 5
    altura  = 10
)

func main() {
    area := largura * altura
    fmt.Println("A área do retângulo é:", area)
}
```

### Exemplo 3: Constantes de tipo string
```go
package main

import "fmt"

const saudacao = "Olá, Mundo!"

func main() {
    fmt.Println(saudacao)
}
```

## Explicação
Embora as constantes sejam uma ferramenta poderosa, é importante lembrar que:
- Constantes não podem ser usadas em todos os contextos. Por exemplo, você não pode usar uma constante para definir o tamanho de um array.
- Ao declarar constantes, tenha cuidado com a sobrecarga de valores. Por exemplo, se você declarar duas constantes com o mesmo nome em escopos diferentes, isso pode levar a confusão.
- As constantes não podem ser variáveis. Uma vez definidas, seu valor não pode ser alterado durante a execução do programa.

## Resumo em Uma Linha
O comando `const` em Go é utilizado para declarar constantes, permitindo a definição de valores fixos que não podem ser alterados ao longo da execução do programa.