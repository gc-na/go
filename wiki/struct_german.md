<!--
Meta Description: # Go Structs: Eine umfassende Einführung in die Datenstruktur in Go ## Synopsis In der Programmiersprache Go ist ein `struct` eine benutzerdefinierte ...
Meta Keywords: struct, die, von, felder, der
-->

# Go Structs: Eine umfassende Einführung in die Datenstruktur in Go

## Synopsis
In der Programmiersprache Go ist ein `struct` eine benutzerdefinierte Datenstruktur, die es ermöglicht, mehrere Datenfelder unter einem gemeinsamen Namen zu gruppieren. Sie dient der Organisation von Daten und der Definition komplexer Datentypen.

## Documentation
Ein `struct` in Go ist eine Sammlung von Feldern, die verschiedene Datentypen enthalten können. Es ermöglicht Entwicklern, zusammengehörige Daten in einer einzigen Einheit zu kapseln. Die Syntax zur Definition eines `struct` ist einfach und intuitiv, was die Lesbarkeit und Wartbarkeit des Codes erhöht.

### Definition eines Structs
Um ein `struct` zu definieren, verwenden Sie das Schlüsselwort `type` gefolgt von dem Namen des `struct` und der Definition der Felder:

```go
type Person struct {
    Name string
    Alter int
    Wohnort string
}
```

### Erstellen von Instanzen
Um eine Instanz eines `struct` zu erstellen, verwenden Sie die Struktur, gefolgt von geschweiften Klammern:

```go
p := Person{
    Name:    "Max Mustermann",
    Alter:   30,
    Wohnort: "Berlin",
}
```

### Zugriff auf Felder
Auf die Felder eines `struct` kann über den Punktoperator (`.`) zugegriffen werden:

```go
fmt.Println(p.Name) // Ausgabe: Max Mustermann
```

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `structs` in Go:

### Beispiel 1: Einfaches Struct
```go
package main

import "fmt"

type Auto struct {
    Marke  string
    Modell string
    Baujahr int
}

func main() {
    fahrzeug := Auto{"Volkswagen", "Golf", 2020}
    fmt.Println(fahrzeug.Marke) // Ausgabe: Volkswagen
}
```

### Beispiel 2: Structs mit Methoden
```go
package main

import "fmt"

type Rechteck struct {
    Breite  float64
    Hoehe   float64
}

func (r Rechteck) Fläche() float64 {
    return r.Breite * r.Hoehe
}

func main() {
    meinRechteck := Rechteck{Breite: 5, Hoehe: 10}
    fmt.Println(meinRechteck.Fläche()) // Ausgabe: 50
}
```

## Explanation
Beim Arbeiten mit `structs` in Go gibt es einige häufige Fallstricke:

1. **Uninitialisierte Felder**: Wenn Sie ein `struct` ohne initialisierte Felder erstellen, nimmt Go für numerische Felder den Wert 0 und für Strings den leeren String an. Achten Sie darauf, die Felder richtig zu initialisieren.

2. **Zugriffsrechte**: Felder, die mit einem Kleinbuchstaben beginnen, sind nur innerhalb des Pakets sichtbar, während Großbuchstaben für die Sichtbarkeit außerhalb des Pakets sorgen. Dies kann zu Verwirrung führen, wenn Sie versuchen, auf Felder aus anderen Paketen zuzugreifen.

3. **Verwendung von Zeigern**: Bei der Übergabe von `structs` an Funktionen kann die Verwendung von Zeigern nützlich sein, um die Effizienz zu verbessern und Änderungen an der ursprünglichen Datenstruktur zu ermöglichen.

## One Line Summary
Ein `struct` in Go ist eine benutzerdefinierte Datenstruktur zur Gruppierung verschiedener Datentypen unter einem gemeinsamen Namen.