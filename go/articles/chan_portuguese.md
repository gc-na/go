<!--
Meta Description: # Uso de `chan` em Go: Comunicação entre Goroutines ## Sinopse O `chan` é uma construção fundamental em Go que permite a comunicação e a sincronização...
Meta Keywords: que, canal, para, chan, uma
-->

# Uso de `chan` em Go: Comunicação entre Goroutines

## Sinopse
O `chan` é uma construção fundamental em Go que permite a comunicação e a sincronização entre goroutines. Ele possibilita a passagem de dados de forma segura entre diferentes partes de um programa, facilitando a concorrência.

## Documentação
### O que é `chan`?
Em Go, um canal (`chan`) é um tipo de dado que serve como um meio de comunicação entre goroutines. Ele permite que uma goroutine envie dados para outra, garantindo que a troca de informações seja feita de maneira segura e controlada. Os canais são essenciais para a construção de aplicações concorrentes, pois ajudam a evitar condições de corrida e a gerenciar o acesso a recursos compartilhados.

### Como usar `chan`
Para criar um canal em Go, utiliza-se a palavra-chave `make` junto com o tipo de dado que será transmitido. O formato básico para a criação de um canal é:

```go
ch := make(chan Tipo)
```

Onde `Tipo` é o tipo de dado que o canal irá transportar. Os canais podem ser unidirecionais ou bidirecionais, dependendo de como são definidos.

#### Enviando e recebendo dados
Para enviar dados para um canal, utiliza-se a operação de envio (`<-`):

```go
ch <- valor
```

Para receber dados de um canal, utiliza-se a operação de recebimento:

```go
valor := <-ch
```

### Detalhes importantes
- **Buffering**: Canais podem ser não-buffered (sem capacidade) ou buffered (com capacidade). Um canal buffered permite que um número específico de valores seja enviado antes que a goroutine que envia bloqueie.
- **Fechamento**: Um canal pode ser fechado usando a função `close(ch)`, o que indica que nenhum valor adicional será enviado. É importante que as goroutines que recebem do canal tratem o fechamento corretamente.

## Exemplos
### Exemplo Básico de Uso de `chan`
```go
package main

import (
    "fmt"
)

func main() {
    ch := make(chan string)

    go func() {
        ch <- "Olá, Goroutine!"
    }()

    mensagem := <-ch
    fmt.Println(mensagem)
}
```

### Exemplo com Canal Buffered
```go
package main

import (
    "fmt"
)

func main() {
    ch := make(chan int, 2) // Canal com capacidade para 2 inteiros

    ch <- 1
    ch <- 2

    fmt.Println(<-ch)
    fmt.Println(<-ch)
}
```

## Explicação
### Armadilhas Comuns
- **Bloqueio**: Se uma goroutine tenta enviar um valor para um canal sem que haja outra goroutine pronta para receber, ela ficará bloqueada. Isso pode causar deadlocks se não for tratado corretamente.
- **Fechamento do Canal**: É uma boa prática fechar canais quando não são mais necessários. Contudo, é importante que nenhuma goroutine esteja tentando enviar dados para um canal fechado, pois isso resultará em um panic.

### Notas Adicionais
- Canais podem ser usados para sincronização, permitindo que uma goroutine espere até que outra conclua uma tarefa.
- Para evitar deadlocks, é essencial planejar a lógica de envio e recebimento com cuidado.

## Resumo em Uma Linha
O `chan` em Go é uma estrutura que facilita a comunicação segura entre goroutines, possibilitando a troca de dados e a sincronização de tarefas.