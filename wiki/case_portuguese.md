<!--
Meta Description: # A Estrutura de Controle "case" em Go: Entenda Como Usá-la ## Sinopse A estrutura de controle `case` em Go permite a seleção condicional entre difere...
Meta Keywords: case, fmt, switch, println, código
-->

# A Estrutura de Controle "case" em Go: Entenda Como Usá-la

## Sinopse
A estrutura de controle `case` em Go permite a seleção condicional entre diferentes alternativas, facilitando a execução de blocos de código com base no valor de uma variável.

## Documentação
O `case` é utilizado dentro da declaração `switch` em Go. Ele permite que você compare uma variável com várias opções possíveis e execute o código correspondente ao primeiro caso que corresponder. A sintaxe básica de um `switch` é a seguinte:

```go
switch expressão {
case valor1:
    // Código a ser executado se expressão == valor1
case valor2:
    // Código a ser executado se expressão == valor2
default:
    // Código a ser executado se nenhum caso anterior for satisfeito
}
```

### Propósito
A estrutura `case` é frequentemente utilizada para simplificar o código e torná-lo mais legível, substituindo múltiplas declarações `if-else`. Ele é especialmente útil quando você tem várias condições baseadas no mesmo valor.

### Uso
- **Comparação de valores**: Você pode usar `case` para comparar uma variável a literais, como inteiros, strings ou outros tipos.
- **Execução de múltiplos casos**: É possível agrupar múltiplos valores em um único `case` separando-os por vírgulas.
- **Case sem expressão**: Um `switch` pode ser usado sem uma expressão, onde o valor padrão será `true`, permitindo que você escreva condições booleanas diretamente.

## Exemplos

### Exemplo Básico
```go
package main

import "fmt"

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

### Agrupando Casos
```go
package main

import "fmt"

func main() {
    nota := 85

    switch nota {
    case 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100:
        fmt.Println("Aprovado com louvor")
    case 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89:
        fmt.Println("Aprovado")
    default:
        fmt.Println("Reprovado")
    }
}
```

### Switch Sem Expressão
```go
package main

import "fmt"

func main() {
    x := 15

    switch {
    case x < 10:
        fmt.Println("Menor que 10")
    case x < 20:
        fmt.Println("Entre 10 e 20")
    default:
        fmt.Println("20 ou mais")
    }
}
```

## Explicação
Ao usar `case`, é importante ficar atento a alguns pontos:

- **Ordem dos casos**: O Go avalia os casos na ordem em que aparecem. O primeiro caso que corresponder será o único executado.
- **Falta de `break`**: Ao contrário de outras linguagens, o Go não precisa de uma instrução `break` para evitar a execução de casos subsequentes. Cada `case` termina automaticamente o `switch`.
- **Valores do `case`**: Os valores dos `case` devem ser do mesmo tipo que a expressão do `switch`. Se não forem compatíveis, o compilador apresentará um erro.

## Resumo em Uma Frase
A estrutura `case` em Go, utilizada dentro do `switch`, permite a seleção condicional de blocos de código com base no valor de uma variável, tornando o código mais limpo e legível.