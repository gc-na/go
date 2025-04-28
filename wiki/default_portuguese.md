<!--
Meta Description: # O Uso da Palavra-Chave "default" na Linguagem Go ## Sinopse A palavra-chave "default" na linguagem de programação Go é utilizada em estruturas de co...
Meta Keywords: default, switch, case, fmt, que
-->

# O Uso da Palavra-Chave "default" na Linguagem Go

## Sinopse
A palavra-chave "default" na linguagem de programação Go é utilizada em estruturas de controle de fluxo, como o `switch`, para especificar um caso padrão que será executado quando nenhuma das condições anteriores for atendida.

## Documentação
A palavra-chave `default` é um elemento importante em instruções `switch`. Ela permite que você forneça um comportamento padrão para um conjunto de condições. Se nenhuma das condições especificadas nas cláusulas `case` for verdadeira, o bloco de código associado ao `default` será executado. Esta funcionalidade é crucial para garantir que um programa tenha um comportamento previsível, mesmo quando as entradas não se encaixam nas condições esperadas.

### Estrutura do `switch` com `default`
A sintaxe básica do `switch` com `default` é a seguinte:

```go
switch expressão {
case valor1:
    // Código a ser executado se a expressão for igual a valor1
case valor2:
    // Código a ser executado se a expressão for igual a valor2
default:
    // Código a ser executado se nenhum caso anterior for verdadeiro
}
```

### Uso
O `default` é opcional em um `switch`. Se omitido e nenhuma correspondência for encontrada, o controle não executará nenhum bloco de código. O `default` pode aparecer em qualquer lugar dentro do `switch`, mas é comum colocá-lo no final da estrutura para maior clareza.

## Exemplos

### Exemplo 1: Uso Básico do `default`

```go
package main

import (
    "fmt"
)

func main() {
    dia := 3

    switch dia {
    case 1:
        fmt.Println("Domingo")
    case 2:
        fmt.Println("Segunda-feira")
    case 3:
        fmt.Println("Terça-feira")
    default:
        fmt.Println("Dia inválido")
    }
}
```
**Saída:** Terça-feira

### Exemplo 2: `default` sem Correspondência

```go
package main

import (
    "fmt"
)

func main() {
    fruta := "laranja"

    switch fruta {
    case "maçã":
        fmt.Println("Você escolheu uma maçã!")
    case "banana":
        fmt.Println("Você escolheu uma banana!")
    default:
        fmt.Println("Fruta não reconhecida.")
    }
}
```
**Saída:** Fruta não reconhecida.

## Explicação
Um erro comum ao usar o `default` é esquecer de incluí-lo em situações onde as entradas podem não corresponder a nenhum caso. Isso pode resultar em um comportamento inesperado, já que o programa não executará nenhuma ação. Além disso, a ordem dos casos é importante; o Go avalia as condições na sequência em que aparecem. Caso um caso específico seja verdadeiro, o `default` não será executado, mesmo que apareça posteriormente.

### Observações Adicionais
- O `default` pode ser usado em `switch` que não se baseiam em valores inteiros ou strings, como em `switch` que avaliam expressões booleanas.
- O bloco `default` pode conter múltiplas instruções, assim como os blocos de `case`.

## Resumo em Uma Linha
A palavra-chave `default` em Go é utilizada em instruções `switch` para definir um comportamento padrão quando nenhum dos casos especificados é atendido.