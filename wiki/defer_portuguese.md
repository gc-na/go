<!--
Meta Description: # Defer em Go: Compreendendo o Comando para Execução Diferida ## Sinopse O comando `defer` na linguagem de programação Go permite que funções sejam ch...
Meta Keywords: defer, função, que, main, fmt
-->

# Defer em Go: Compreendendo o Comando para Execução Diferida

## Sinopse
O comando `defer` na linguagem de programação Go permite que funções sejam chamadas de forma diferida, ou seja, sua execução é agendada para ocorrer após a conclusão da função que a contém. Essa característica é especialmente útil para garantir que certas ações, como o fechamento de arquivos ou a liberação de recursos, sejam sempre executadas, independentemente de como a função termina.

## Documentação
### Propósito
O `defer` é utilizado para adiar a execução de uma função até que a função que a chamou tenha sido finalizada. Isso é útil para garantir a limpeza de recursos, como liberar memória ou fechar conexões, mesmo que ocorra um erro ou um retorno antecipado da função.

### Uso
O comando `defer` é seguido pela chamada de uma função. Quando a função que contém o `defer` retorna, todas as funções deferidas são executadas na ordem inversa em que foram declaradas. Isso significa que o último `defer` a ser declarado será o primeiro a ser executado.

### Detalhes
- A execução de funções deferidas ocorre mesmo se ocorrer um pânico ou erro dentro da função.
- Os argumentos das funções deferidas são avaliados imediatamente, mas a execução da função em si é postergada.
- O uso excessivo de `defer` pode impactar a performance, especialmente em loops, devido ao overhead que causa.

## Exemplos
### Exemplo Básico
```go
package main

import (
    "fmt"
)

func main() {
    defer fmt.Println("Executando após a função main")
    fmt.Println("Executando a função main")
}
```
**Saída:**
```
Executando a função main
Executando após a função main
```

### Exemplo com Funções Deferidas em Ordem
```go
package main

import (
    "fmt"
)

func main() {
    defer fmt.Println("Primeiro defer")
    defer fmt.Println("Segundo defer")
    fmt.Println("Executando a função main")
}
```
**Saída:**
```
Executando a função main
Segundo defer
Primeiro defer
```

## Explicação
### Armadilhas Comuns
- **Argumentos Avaliados Imediatamente**: É importante lembrar que os argumentos da função deferida são avaliados no momento em que a declaração do `defer` é encontrada, e não no momento em que a função é executada. Isso pode levar a comportamentos inesperados se não for compreendido corretamente.
  
```go
package main

import "fmt"

func main() {
    x := 5
    defer fmt.Println(x) // x é avaliado aqui
    x = 10
}
```
**Saída:**
```
5
```

- **Performance em Loops**: Usar `defer` dentro de loops pode impactar a performance, pois cada chamada deferida adiciona overhead. É frequentemente recomendado evitar `defer` em loops críticos de desempenho.

### Nota Adicional
O uso de `defer` é uma prática comum em Go para garantir que a limpeza de recursos seja realizada, especialmente em operações que podem falhar, como abrir arquivos ou conexões de rede. É uma maneira elegante de garantir que o código permaneça limpo e fácil de entender.

## Resumo em Uma Linha
O `defer` em Go permite a execução de funções de forma diferida, garantindo a limpeza de recursos ao final da execução da função que as contém.