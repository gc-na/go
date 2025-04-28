<!--
Meta Description: # int8 em Go: Entendendo o Tipo de Dados Inteiro ## Sinopse O tipo `int8` em Go é um tipo de dado inteiro de 8 bits que armazena valores inteiros no i...
Meta Keywords: int8, tipo, uma, que, 127
-->

# int8 em Go: Entendendo o Tipo de Dados Inteiro

## Sinopse
O tipo `int8` em Go é um tipo de dado inteiro de 8 bits que armazena valores inteiros no intervalo de -128 a 127. Este artigo explora suas características, usos e exemplos práticos.

## Documentação
O `int8` é um dos tipos primitivos disponíveis na linguagem de programação Go. Ele é utilizado para representar números inteiros pequenos, oferecendo uma forma eficiente de armazenar dados quando o espaço de memória é uma preocupação. O tipo `int8` ocupa 1 byte de memória, o que o torna ideal para situações onde a economia de espaço é necessária.

### Propósito
O propósito do `int8` é permitir a manipulação de números inteiros dentro de um intervalo específico, economizando recursos de memória em comparação com tipos maiores, como `int` ou `int32`.

### Uso
O `int8` pode ser usado em operações aritméticas, lógica e comparações. É frequentemente utilizado em situações onde os valores esperados estão dentro do intervalo de -128 a 127 e a eficiência de memória é uma prioridade.

### Detalhes
- **Declaração**: Para declarar uma variável do tipo `int8`, você pode usar a palavra-chave `var` ou a declaração curta com `:=`. Exemplo: `var x int8 = 100` ou `y := int8(50)`.
- **Conversão**: É possível converter outros tipos numéricos para `int8`, desde que o valor resultante esteja dentro do intervalo permitido.
- **Aritmética**: Operações aritméticas com `int8` seguem as mesmas regras dos números inteiros, mas é importante lembrar que os resultados também devem ser tratados como `int8` para evitar overflow.

## Exemplos
```go
package main

import "fmt"

func main() {
	// Declaração de uma variável int8
	var a int8 = 100
	var b int8 = 27

	// Operação de adição
	var soma int8 = a + b
	fmt.Println("Soma:", soma) // Saída: Soma: 127

	// Tentativa de overflow
	var c int8 = 127
	c += 1 // Isso causará um overflow
	fmt.Println("Valor após overflow:", c) // Saída: Valor após overflow: -128
}
```

## Explicação
Um erro comum ao usar `int8` é o `overflow`, que ocorre quando o resultado de uma operação aritmética excede o limite máximo ou mínimo do tipo. No exemplo acima, adicionar 1 a 127 resulta em -128, devido ao comportamento de wrap-around do tipo `int8`. 

Outro ponto a considerar é a conversão entre tipos. Tentar atribuir um valor fora do intervalo de `int8` sem conversão adequada pode gerar erros de compilação. Portanto, sempre verifique e converta os valores apropriadamente.

## Resumo em Uma Linha
O tipo `int8` em Go é um inteiro de 8 bits que representa valores entre -128 e 127, ideal para economizar memória em operações numéricas.