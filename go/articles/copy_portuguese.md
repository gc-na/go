<!--
Meta Description: # Comando "copy" em Go: Transferindo Dados de Forma Eficiente ## Sinopse O comando `copy` em Go é uma função essencial que permite copiar dados de um ...
Meta Keywords: slice, copy, para, destino, função
-->

# Comando "copy" em Go: Transferindo Dados de Forma Eficiente

## Sinopse
O comando `copy` em Go é uma função essencial que permite copiar dados de um slice para outro, facilitando a manipulação e transferência de informações em memória de maneira eficiente.

## Documentação

### Propósito
A função `copy` é utilizada para copiar elementos de um slice (ou array) de origem para um slice de destino. Essa operação é útil em diversas situações, como ao manipular dados, realizar operações de backup ou quando se deseja modificar um slice sem alterar o original.

### Uso
A função `copy` possui a seguinte assinatura:

```go
func copy(dst, src []Type) int
```

- **dst**: O slice de destino onde os dados serão copiados.
- **src**: O slice de origem de onde os dados serão copiados.
- **Type**: O tipo dos elementos contidos nos slices, que deve ser o mesmo para ambos.

O retorno da função `copy` é um inteiro que indica o número de elementos copiados. O número de elementos copiados é igual ao menor tamanho entre os slices de origem e destino.

### Detalhes
- Se o slice de origem for menor que o de destino, apenas os elementos do slice de origem serão copiados.
- Se o slice de destino for menor que o de origem, apenas os elementos até o tamanho do slice de destino serão copiados.
- A função `copy` não aloca memória para o slice de destino; ele deve ser inicializado antes da cópia.

## Exemplos

### Exemplo Básico de Uso
```go
package main

import "fmt"

func main() {
    src := []int{1, 2, 3, 4, 5}
    dst := make([]int, 3)

    n := copy(dst, src)
    fmt.Println(dst) // Saída: [1 2 3]
    fmt.Println(n)   // Saída: 3
}
```

### Exemplo com Slices de Diferentes Tamanhos
```go
package main

import "fmt"

func main() {
    src := []string{"a", "b", "c", "d"}
    dst := make([]string, 2)

    n := copy(dst, src)
    fmt.Println(dst) // Saída: [a b]
    fmt.Println(n)   // Saída: 2
}
```

## Explicação
- **Cuidado com o Tamanho**: Ao utilizar a função `copy`, é essencial garantir que o slice de destino tenha o tamanho apropriado para evitar perda de dados.
- **Memória**: A função `copy` não realiza a alocação de memória para o slice de destino. Portanto, ele deve ser inicializado corretamente para receber os dados.
- **Performance**: A operação de cópia é otimizada em Go, mas ainda assim, deve ser usada com critério para evitar cópias desnecessárias, que podem impactar a performance em aplicações críticas.

## Resumo em Uma Linha
A função `copy` em Go permite copiar eficientemente elementos de um slice para outro, respeitando o tamanho mínimo entre eles.