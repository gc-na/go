<!--
Meta Description: # Comando "return" em Go: Entenda como Funciona e Suas Aplicações ## Sinopse O comando `return` em Go é utilizado para encerrar a execução de uma funç...
Meta Keywords: return, valores, função, uma, que
-->

# Comando "return" em Go: Entenda como Funciona e Suas Aplicações

## Sinopse
O comando `return` em Go é utilizado para encerrar a execução de uma função e, opcionalmente, retornar um ou mais valores para o chamador. Este artigo explora sua finalidade, uso e exemplos práticos.

## Documentação
O `return` é uma instrução fundamental em Go que permite que uma função devolva valores ao seu chamador. Quando uma função é chamada, ela pode realizar diversas operações e, ao final, pode enviar um resultado de volta. O uso do `return` é simples e essencial para o fluxo de dados em programas Go.

### Propósito
- Encerrar a execução de uma função.
- Retornar valores para a função chamadora.

### Uso
A sintaxe básica do `return` é:

```go
return [valores]
```

Você pode retornar um ou mais valores, dependendo da assinatura da função. Para funções sem retorno, o `return` pode ser usado sem especificar valores.

### Detalhes
- **Funções sem retorno**: É possível usar `return` em funções que não retornam valores, simplesmente para sair da função.
- **Múltiplos valores**: Go permite que você retorne múltiplos valores, o que é uma característica poderosa da linguagem.
- **Nomeados**: Em funções com parâmetros de retorno nomeados, você pode usar `return` sem especificar os valores, e os valores nomeados serão retornados automaticamente.

## Exemplos

### Exemplo 1: Função Simples com Retorno
```go
package main

import "fmt"

func soma(a int, b int) int {
    return a + b
}

func main() {
    resultado := soma(5, 3)
    fmt.Println("Resultado da soma:", resultado)
}
```

### Exemplo 2: Função com Múltiplos Valores
```go
package main

import "fmt"

func dividir(a, b int) (int, int) {
    quociente := a / b
    resto := a % b
    return quociente, resto
}

func main() {
    q, r := dividir(10, 3)
    fmt.Println("Quociente:", q, "Resto:", r)
}
```

### Exemplo 3: Função Sem Retorno
```go
package main

import "fmt"

func mensagem() {
    fmt.Println("Esta função não retorna nada.")
    return // Saída da função sem retornar valores
}

func main() {
    mensagem()
}
```

## Explicação
Um erro comum ao usar `return` é esquecer de especificar valores em funções que esperam um retorno, o que resulta em um erro de compilação. Além disso, ao usar funções com múltiplos valores, é importante garantir que todas as variáveis sejam tratadas corretamente no lado do chamador.

Outra armadilha é o uso do `return` em funções de goroutines, onde a lógica de retorno pode não se comportar como esperado devido à natureza concorrente das goroutines. É fundamental entender que, se uma goroutine é iniciada, o `return` não afetará a execução da goroutine em andamento.

## Resumo em Uma Linha
O comando `return` em Go encerra a execução de uma função e retorna valores para o chamador, permitindo um controle eficaz do fluxo de dados no programa.