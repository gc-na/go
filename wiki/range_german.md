<!--
Meta Description: # Der "range"-Befehl in Go: Effiziente Iteration über Datenstrukturen ## Synopsis Der `range`-Befehl in der Programmiersprache Go ermöglicht eine einf...
Meta Keywords: der, range, und, index, über
-->

# Der "range"-Befehl in Go: Effiziente Iteration über Datenstrukturen

## Synopsis
Der `range`-Befehl in der Programmiersprache Go ermöglicht eine einfache und effiziente Iteration über verschiedene Datenstrukturen wie Arrays, Slices, Maps und Channels. Er vereinfacht das Durchlaufen von Daten und das Erhalten von Index und Wert.

## Dokumentation
Der `range`-Befehl wird in Go verwendet, um über Datenstrukturen zu iterieren. Er kann in einer `for`-Schleife genutzt werden und bietet eine klare Syntax, um sowohl den Index als auch den Wert des Elements zu erhalten.

### Verwendung
Der grundlegende Syntax für die Verwendung von `range` ist wie folgt:

```go
for index, value := range collection {
    // Logik hier
}
```

Hierbei wird `collection` durch die jeweilige Datenstruktur ersetzt, über die iteriert werden soll. Es ist auch möglich, nur den Wert oder nur den Index zu erhalten:

- Nur Wert:
  ```go
  for _, value := range collection {
      // Logik hier
  }
  ```

- Nur Index:
  ```go
  for index := range collection {
      // Logik hier
  }
  ```

### Details
- `range` kann auf Folgendes angewendet werden:
  - **Arrays und Slices**: Gibt den Index und den Wert des jeweiligen Elements zurück.
  - **Maps**: Gibt den Schlüssel und den Wert zurück.
  - **Channels**: Gibt den Wert zurück, der vom Kanal empfangen wird.

## Beispiele
Hier sind einige grundlegende Beispiele zur Veranschaulichung der Verwendung von `range`:

### Beispiel 1: Iteration über ein Slice
```go
package main

import "fmt"

func main() {
    fruits := []string{"Apfel", "Banane", "Kirsche"}
    for index, fruit := range fruits {
        fmt.Printf("Index: %d, Wert: %s\n", index, fruit)
    }
}
```

### Beispiel 2: Iteration über eine Map
```go
package main

import "fmt"

func main() {
    capitals := map[string]string{
        "Deutschland": "Berlin",
        "Frankreich":  "Paris",
        "Spanien":     "Madrid",
    }
    for country, capital := range capitals {
        fmt.Printf("Hauptstadt von %s ist %s\n", country, capital)
    }
}
```

### Beispiel 3: Iteration über einen Channel
```go
package main

import "fmt"

func main() {
    ch := make(chan string)
    go func() {
        ch <- "Hallo"
        ch <- "Welt"
        close(ch)
    }()
    for msg := range ch {
        fmt.Println(msg)
    }
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `range` ist das Verständnis der Variablen, die in der Schleife verwendet werden. Es ist wichtig zu beachten, dass in der Schleife Kopien der Werte erstellt werden, nicht die Originalwerte. Bei Maps und Slices kann dies zu unerwarteten Ergebnissen führen, wenn die Werte von Referenztypen sind.

Ein weiterer Punkt ist, dass beim Iterieren über einen Channel der Channel geschlossen werden muss, um die Schleife zu beenden. Andernfalls kann die Iteration in einer Endlosschleife enden.

## Ein-Satz-Zusammenfassung
Der `range`-Befehl in Go ermöglicht eine einfache und effiziente Iteration über Datenstrukturen wie Arrays, Slices, Maps und Channels.