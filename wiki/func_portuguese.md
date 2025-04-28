<!--
Meta Description: # Func: A Função em Go - Entenda e Domine o Uso ## Sinopse Neste artigo, exploraremos a palavra-chave `func` na linguagem de programação Go, que é fun...
Meta Keywords: func, função, que, resultado, para
-->

# Func: A Função em Go - Entenda e Domine o Uso

## Sinopse
Neste artigo, exploraremos a palavra-chave `func` na linguagem de programação Go, que é fundamental para a definição de funções. Aprenda como utilizá-la para estruturar seu código de forma clara e eficiente.

## Documentação
A palavra-chave `func` é utilizada em Go para declarar funções. As funções são blocos de código que podem ser chamados em diferentes partes do seu programa, permitindo a reutilização e a organização do código. 

### Propósito
A principal finalidade da palavra-chave `func` é criar funções que podem receber parâmetros e retornar valores, facilitando a modularização do código.

### Uso
A sintaxe básica para declarar uma função em Go é a seguinte:

```go
func NomeDaFuncao(parametros) tipoRetorno {
    // corpo da função
}
```

- **NomeDaFuncao**: O nome que você escolhe para a função.
- **parametros**: Lista de parâmetros que a função aceita, incluindo seus tipos.
- **tipoRetorno**: O tipo de dado que a função retorna (caso haja um retorno).

### Exemplo de Uso
Aqui estão alguns exemplos básicos de como utilizar `func` em Go:

```go
package main

import "fmt"

// Função que soma dois inteiros e retorna o resultado
func somar(a int, b int) int {
    return a + b
}

func main() {
    resultado := somar(5, 3)
    fmt.Println("Resultado da soma:", resultado) // Saída: Resultado da soma: 8
}
```

```go
package main

import "fmt"

// Função sem parâmetros que retorna uma string
func saudacao() string {
    return "Olá, Mundo!"
}

func main() {
    fmt.Println(saudacao()) // Saída: Olá, Mundo!
}
```

## Explicação
Ao utilizar funções em Go, é importante estar ciente de algumas armadilhas e detalhes comuns:

1. **Nomes de Funções**: O nome da função deve ser descritivo para facilitar a leitura do código.
2. **Visibilidade**: Se o nome da função começa com uma letra maiúscula, ela é exportada (visível para outros pacotes). Se começar com uma letra minúscula, é privada ao pacote.
3. **Retorno Múltiplo**: Go permite que funções retornem múltiplos valores. Isto é útil em várias situações, como quando você deseja retornar um valor e um erro.

Exemplo de retorno múltiplo:

```go
package main

import "fmt"

// Função que divide dois números e retorna o resultado e um erro
func dividir(a, b float64) (float64, error) {
    if b == 0 {
        return 0, fmt.Errorf("divisão por zero")
    }
    return a / b, nil
}

func main() {
    resultado, err := dividir(10, 2)
    if err != nil {
        fmt.Println("Erro:", err)
    } else {
        fmt.Println("Resultado da divisão:", resultado) // Saída: Resultado da divisão: 5
    }
}
```

## Resumo em Uma Linha
A palavra-chave `func` em Go é usada para declarar funções, permitindo a modularização e a reutilização de código de forma eficiente e organizada.