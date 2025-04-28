<!--
Meta Description: # Estruturas em Go: Como Utilizar "struct" de Forma Eficiente ## Sinopse As estruturas (structs) em Go são tipos de dados compostos que permitem agrup...
Meta Keywords: estruturas, campos, uma, estrutura, struct
-->

# Estruturas em Go: Como Utilizar "struct" de Forma Eficiente

## Sinopse
As estruturas (structs) em Go são tipos de dados compostos que permitem agrupar diferentes tipos de dados em uma única unidade, facilitando a organização e manipulação de informações complexas.

## Documentação
As estruturas em Go são definidas usando a palavra-chave `type` seguida do nome da estrutura e da palavra-chave `struct`. Elas são particularmente úteis para modelar dados complexos e podem conter campos de diferentes tipos, incluindo outros structs.

### Definição de uma Estrutura
Para definir uma estrutura, utilize a seguinte sintaxe:

```go
type NomeDaEstrutura struct {
    Campo1 Tipo1
    Campo2 Tipo2
}
```

### Criação de Instâncias
Instâncias de estruturas podem ser criadas de várias formas, como demonstrado abaixo:

```go
pessoa := NomeDaEstrutura{
    Campo1: valor1,
    Campo2: valor2,
}
```

### Acesso aos Campos
Os campos de uma estrutura podem ser acessados utilizando a notação de ponto:

```go
fmt.Println(pessoa.Campo1)
```

### Métodos em Estruturas
Você pode associar métodos a estruturas, permitindo que elas tenham comportamentos específicos:

```go
func (p *NomeDaEstrutura) MetodoExemplo() {
    // implementação do método
}
```

## Exemplos

### Exemplo 1: Definindo uma Estrutura Simples
```go
package main

import "fmt"

type Carro struct {
    Marca string
    Ano   int
}

func main() {
    meuCarro := Carro{
        Marca: "Fusca",
        Ano:   1976,
    }
    fmt.Println(meuCarro.Marca, meuCarro.Ano)
}
```

### Exemplo 2: Métodos de Estrutura
```go
package main

import "fmt"

type Retangulo struct {
    Largura, Altura float64
}

func (r Retangulo) Area() float64 {
    return r.Largura * r.Altura
}

func main() {
    ret := Retangulo{Largura: 10, Altura: 5}
    fmt.Println("Área do retângulo:", ret.Area())
}
```

## Explicação
Um erro comum ao trabalhar com structs é a inicialização incorreta. É crucial garantir que todos os campos sejam inicializados corretamente para evitar valores zero inesperados. Além disso, tenha cuidado ao usar ponteiros para estruturas, pois isso pode levar a problemas de concorrência se não for tratado adequadamente.

Outro ponto a se considerar é a visibilidade dos campos. Campos com a primeira letra maiúscula são exportados e podem ser acessados fora do pacote, enquanto campos com a primeira letra minúscula são privados, limitando seu acesso apenas ao pacote onde foram definidos.

## Resumo em Uma Linha
As estruturas em Go permitem a criação de tipos de dados personalizados, facilitando a organização e manipulação de informações complexas.