<!--
Meta Description: # A Palavra-chave "var" em Go: Declaração de Variáveis ## Sinopse A palavra-chave `var` em Go é utilizada para declarar variáveis, permitindo a criaçã...
Meta Keywords: var, declaração, variáveis, para, int
-->

# A Palavra-chave "var" em Go: Declaração de Variáveis

## Sinopse
A palavra-chave `var` em Go é utilizada para declarar variáveis, permitindo a criação de identificadores que armazenam dados de diversos tipos, contribuindo para a flexibilidade e organização do código.

## Documentação
A declaração de variáveis em Go é fundamental para o armazenamento e manipulação de dados. A sintaxe básica para declarar uma variável utilizando `var` é:

```go
var nomeDaVariavel tipo
```

### Propósito
O propósito da palavra-chave `var` é introduzir uma nova variável em um espaço de nome específico, que pode ser utilizada ao longo do escopo em que foi declarada. A palavra-chave pode ser usada tanto em nível de função quanto em nível de pacote.

### Uso
As variáveis podem ser declaradas de várias maneiras:

1. **Declaração Simples**:
   ```go
   var x int
   ```

2. **Declaração com Inicialização**:
   ```go
   var x int = 10
   ```

3. **Declaração de Múltiplas Variáveis**:
   ```go
   var x, y int = 1, 2
   ```

4. **Declaração com Inferência de Tipo**:
   ```go
   var x = 10 // O tipo é inferido como int
   ```

5. **Declaração em Blocos**:
   ```go
   var (
       a int
       b string
   )
   ```

## Exemplos

### Exemplo 1: Declaração Simples
```go
package main

import "fmt"

func main() {
    var numero int
    numero = 42
    fmt.Println(numero)
}
```

### Exemplo 2: Inicialização
```go
package main

import "fmt"

func main() {
    var nome string = "Maria"
    fmt.Println(nome)
}
```

### Exemplo 3: Declaração Múltipla
```go
package main

import "fmt"

func main() {
    var a, b int = 5, 10
    fmt.Println(a + b)
}
```

### Exemplo 4: Inferência de Tipo
```go
package main

import "fmt"

func main() {
    var valor = 3.14 // tipo float64
    fmt.Println(valor)
}
```

## Explicação
Embora a palavra-chave `var` seja uma ferramenta poderosa, alguns pontos devem ser considerados:

- **Escopo**: Variáveis declaradas com `var` têm escopo global se definidas fora de funções e escopo local se definidas dentro de uma função.
- **Zero Values**: Variáveis declaradas mas não inicializadas com `var` recebem valores zero para seu tipo correspondente (ex: `0` para `int`, `""` para `string`, etc.).
- **Não é Necessário Usar `var`**: Para declarações locais, pode-se usar a sintaxe de atribuição curta `:=`, que é mais concisa.

### Armadilhas Comuns
- Tentativa de reatribuir uma variável de tipo diferente após a declaração. Go é uma linguagem tipada estaticamente, e isso não é permitido.
- Múltiplas declarações de variáveis com o mesmo nome no mesmo escopo resultam em erro de compilação.

## Resumo em Uma Linha
A palavra-chave `var` em Go é usada para declarar variáveis, permitindo a criação de identificadores que armazenam dados de diferentes tipos dentro de um escopo definido.