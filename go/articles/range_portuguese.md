<!--
Meta Description: # Uso da Palavra-chave "range" em Go: Iteração Eficiente em Estruturas de Dados ## Sinopse A palavra-chave "range" em Go é uma ferramenta poderosa par...
Meta Keywords: range, sobre, canal, chave, iterar
-->

# Uso da Palavra-chave "range" em Go: Iteração Eficiente em Estruturas de Dados

## Sinopse
A palavra-chave "range" em Go é uma ferramenta poderosa para iterar sobre arrays, slices, maps e canais, facilitando o acesso a elementos e suas respectivas posições dentro dessas estruturas de dados.

## Documentação
A palavra-chave `range` é utilizada para iterar sobre elementos de diferentes tipos de coleções em Go. Sua sintaxe varia dependendo do tipo de estrutura que está sendo percorrida. O `range` não apenas fornece os elementos, mas também pode oferecer o índice ou a chave, dependendo do contexto.

### Uso Básico
- **Arrays e Slices**: Ao iterar sobre arrays ou slices, `range` retorna o índice e o valor correspondente.
- **Maps**: Quando utilizado em maps, `range` retorna a chave e o valor.
- **Canais**: No caso de canais, `range` itera sobre os valores recebidos até que o canal seja fechado.

### Sintaxe
```go
for i, v := range collection {
    // Utilize i e v conforme necessário
}
```

### Exemplo de Uso
Abaixo estão exemplos práticos de como usar `range` em diferentes estruturas:

#### Iterando sobre um Slice
```go
package main

import "fmt"

func main() {
    frutas := []string{"maçã", "banana", "laranja"}

    for i, fruta := range frutas {
        fmt.Printf("Índice: %d, Fruta: %s\n", i, fruta)
    }
}
```

#### Iterando sobre um Map
```go
package main

import "fmt"

func main() {
    notas := map[string]int{"João": 90, "Maria": 85, "Pedro": 88}

    for aluno, nota := range notas {
        fmt.Printf("Aluno: %s, Nota: %d\n", aluno, nota)
    }
}
```

#### Iterando sobre um Canal
```go
package main

import "fmt"

func main() {
    canal := make(chan int)

    go func() {
        for i := 0; i < 5; i++ {
            canal <- i
        }
        close(canal)
    }()

    for valor := range canal {
        fmt.Println(valor)
    }
}
```

## Explicação
Embora `range` seja uma ferramenta útil, existem algumas armadilhas comuns a serem observadas:

1. **Referência a Variáveis**: Se você estiver iterando sobre um slice e estiver usando uma variável, lembre-se de que ela será compartilhada em todas as iterações. Para evitar isso, utilize uma variável local dentro do loop se for necessário manter um valor específico.

2. **Mapas e Ordem**: A iteração sobre um map não garante a ordem dos elementos. Se a ordem for importante, considere usar um slice para armazenar as chaves e iterar sobre esse slice.

3. **Canais Fechados**: Ao iterar sobre um canal, o loop `range` continuará até que o canal seja fechado. Certifique-se de que o canal está sendo fechado corretamente em sua implementação.

## Resumo em Uma Linha
A palavra-chave `range` em Go permite iterar de forma eficiente sobre arrays, slices, maps e canais, facilitando o acesso a elementos e suas posições.