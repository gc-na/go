<!--
Meta Description: # Go for Schleife: Nutzung, Beispiele und häufige Fallstricke ## Synopsis Die `for`-Schleife in Go ist eine leistungsstarke und flexible Kontrollstruk...
Meta Keywords: schleife, die, fmt, und, sie
-->

# Go for Schleife: Nutzung, Beispiele und häufige Fallstricke

## Synopsis
Die `for`-Schleife in Go ist eine leistungsstarke und flexible Kontrollstruktur, die es ermöglicht, wiederholte Ausführungen von Codeblöcken durchzuführen. Sie ist das einzige Schleifen-Konstrukt in Go und kann in verschiedenen Formen eingesetzt werden.

## Dokumentation
Die `for`-Schleife ist in Go das primäre Mittel zum Iterieren über Datenstrukturen oder zum wiederholten Ausführen von Code. Sie kann in drei verschiedenen Formen verwendet werden:

1. **Einfacher Zähler**: Diese Form wird häufig verwendet, um einen Codeblock eine bestimmte Anzahl von Malen auszuführen.
   ```go
   for i := 0; i < 10; i++ {
       fmt.Println(i)
   }
   ```

2. **Bedingte Schleife**: Hierbei handelt es sich um eine Schleife, die so lange läuft, wie eine bestimmte Bedingung wahr ist.
   ```go
   i := 0
   for i < 10 {
       fmt.Println(i)
       i++
   }
   ```

3. **Iterieren über Datenstrukturen**: Die `for`-Schleife kann auch verwendet werden, um über Arrays, Slices, Maps und Channels zu iterieren.
   ```go
   fruits := []string{"Apfel", "Banane", "Kirsche"}
   for index, fruit := range fruits {
       fmt.Println(index, fruit)
   }
   ```

Die `for`-Schleife in Go hat keine speziellen Schlüsselwörter für `while` oder `do...while`, da sie durch ihre Flexibilität diese Konzepte problemlos abdeckt.

## Beispiele
### Beispiel 1: Einfache Zähler-Schleife
```go
package main

import "fmt"

func main() {
    for i := 0; i < 5; i++ {
        fmt.Println("Zahl:", i)
    }
}
```

### Beispiel 2: Bedingte Schleife
```go
package main

import "fmt"

func main() {
    i := 0
    for i < 5 {
        fmt.Println("Zahl:", i)
        i++
    }
}
```

### Beispiel 3: Iteration über ein Slice
```go
package main

import "fmt"

func main() {
    zahlen := []int{1, 2, 3, 4, 5}
    for index, zahl := range zahlen {
        fmt.Printf("Index: %d, Zahl: %d\n", index, zahl)
    }
}
```

## Erklärung
Obwohl die `for`-Schleife sehr mächtig ist, gibt es einige häufige Fallstricke:

- **Endlosschleifen**: Achten Sie darauf, die Schleifenbedingung korrekt zu formulieren, um Endlosschleifen zu vermeiden. Eine falsche Bedingung kann dazu führen, dass Ihr Programm nicht mehr reagiert.
  
- **Variable Scope**: Variablen, die in der Schleife deklariert werden, haben einen eingeschränkten Gültigkeitsbereich. Sie sind nur innerhalb der Schleife sichtbar.

- **Break und Continue**: Verwenden Sie `break`, um eine Schleife vorzeitig zu beenden, und `continue`, um die aktuelle Iteration zu überspringen und mit der nächsten fortzufahren. Seien Sie jedoch vorsichtig mit dem Einsatz dieser Schlüsselwörter, da sie die Lesbarkeit des Codes beeinträchtigen können.

## Ein Satz Zusammenfassung
Die `for`-Schleife in Go ist das zentrale Konstrukt für wiederholte Ausführung von Code und bietet vielseitige Anwendungsoptionen.