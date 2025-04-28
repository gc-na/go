<!--
Meta Description: # O Comando "for" em Go: Entenda a Estrutura de Laço de Repetição ## Sinopse O comando "for" em Go é uma estrutura de controle fundamental utilizada p...
Meta Keywords: loop, fmt, range, main, comando
-->

# O Comando "for" em Go: Entenda a Estrutura de Laço de Repetição

## Sinopse
O comando "for" em Go é uma estrutura de controle fundamental utilizada para implementar loops, permitindo a iteração sobre diferentes coleções e a execução repetida de um bloco de código.

## Documentação
O "for" é a única estrutura de loop em Go, substituindo outras construções de repetição como "while" e "do-while" encontradas em outras linguagens. Ele pode ser utilizado de diversas formas, oferecendo flexibilidade e simplicidade.

### Estruturas de Uso

1. **Loop com Contador**:
   ```go
   for i := 0; i < 10; i++ {
       fmt.Println(i)
   }
   ```
   Nesse exemplo, o laço é executado 10 vezes, imprimindo os números de 0 a 9.

2. **Loop Infinito**:
   ```go
   for {
       fmt.Println("Este é um loop infinito")
   }
   ```
   Um loop que nunca termina por si só, podendo ser interrompido com uma instrução `break`.

3. **Iterando sobre Slices e Arrays**:
   ```go
   frutas := []string{"maçã", "banana", "laranja"}
   for i, fruta := range frutas {
       fmt.Printf("%d: %s\n", i, fruta)
   }
   ```
   O comando `range` permite percorrer elementos de um slice ou array, retornando o índice e o valor.

4. **Usando `range` com Mapas**:
   ```go
   pontuacoes := map[string]int{"Alice": 10, "Bob": 20}
   for jogador, score := range pontuacoes {
       fmt.Printf("%s: %d\n", jogador, score)
   }
   ```
   Itera sobre um mapa, permitindo acessar a chave e o valor.

## Exemplos
### Exemplo 1: Loop Básico
```go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println("Iteração:", i)
    }
}
```

### Exemplo 2: Loop Infinito com Condição de Saída
```go
package main

import "fmt"

func main() {
    i := 0
    for {
        if i >= 5 {
            break
        }
        fmt.Println("Contagem:", i)
        i++
    }
}
```

### Exemplo 3: Iteração com `range`
```go
package main

import "fmt"

func main() {
    numeros := []int{1, 2, 3, 4}
    for _, numero := range numeros {
        fmt.Println("Número:", numero)
    }
}
```

## Explicação
Embora o comando "for" seja bastante simples, existem algumas armadilhas comuns a serem evitadas:

- **Loop Infinito Acidental**: Certifique-se de que a condição de saída está corretamente configurada para evitar loops infinitos indesejados.
- **Variáveis de Loop**: Lembre-se de que, ao usar `range`, as variáveis de loop podem ser sobrescritas, causando confusão se você não as utilizar corretamente.
- **Performance**: Ao iterar sobre grandes coleções, considere o impacto de performance e evite operações desnecessárias dentro do laço.

## Resumo em Uma Linha
O comando "for" em Go é uma estrutura de repetição versátil que permite a iteração eficiente sobre coleções e a execução repetida de blocos de código.