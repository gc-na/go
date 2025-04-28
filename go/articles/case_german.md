<!--
Meta Description: # Der `case` Befehl in Go: Bedingte Anweisungen effizient nutzen ## Synopsis Der `case` Befehl in Go wird in Verbindung mit der `switch` Anweisung ver...
Meta Keywords: case, fmt, der, ist, println
-->

# Der `case` Befehl in Go: Bedingte Anweisungen effizient nutzen

## Synopsis
Der `case` Befehl in Go wird in Verbindung mit der `switch` Anweisung verwendet, um alternative Ausführungswege basierend auf dem Wert einer Variable zu definieren. Dies ermöglicht eine klare und lesbare Struktur für komplexe bedingte Logik.

## Documentation
Die `switch` Anweisung in Go ermöglicht die Ausführung eines von mehreren Codeblöcken, abhängig vom Wert einer Variable. Der `case` Befehl dient dazu, spezifische Bedingungen zu definieren, die geprüft werden. Wenn eine Bedingung erfüllt ist, wird der zugehörige Codeblock ausgeführt.

### Syntax
```go
switch variable {
case wert1:
    // Block für wert1
case wert2:
    // Block für wert2
default:
    // Standardblock, wenn keine Bedingung erfüllt ist
}
```

### Verwendung
1. **Einfache Bedingungen**: Der `case` Befehl kann für einfache Vergleiche verwendet werden.
2. **Mehrere Werte**: Ein `case` kann mehrere Werte enthalten, die durch Kommas getrennt sind.
3. **Fall durch `default`**: Der `default` Fall wird ausgeführt, wenn kein anderer `case` zutrifft.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `case` in Go.

### Beispiel 1: Einfache Verwendung
```go
package main

import "fmt"

func main() {
    tag := "Montag"

    switch tag {
    case "Montag":
        fmt.Println("Das ist der erste Tag der Woche.")
    case "Freitag":
        fmt.Println("Das ist der letzte Arbeitstag der Woche.")
    default:
        fmt.Println("Das ist ein anderer Tag.")
    }
}
```

### Beispiel 2: Mehrere Werte in einem `case`
```go
package main

import "fmt"

func main() {
    wochentag := "Samstag"

    switch wochentag {
    case "Samstag", "Sonntag":
        fmt.Println("Wochenende!")
    default:
        fmt.Println("Arbeitstag.")
    }
}
```

### Beispiel 3: Verwendung von `default`
```go
package main

import "fmt"

func main() {
    farbe := "blau"

    switch farbe {
    case "rot":
        fmt.Println("Die Farbe ist Rot.")
    case "grün":
        fmt.Println("Die Farbe ist Grün.")
    default:
        fmt.Println("Unbekannte Farbe.")
    }
}
```

## Explanation
Ein häufiger Fehler ist, nicht zu erkennen, dass `switch` in Go automatisch `break` am Ende jedes `case` einfügt. Dies bedeutet, dass der Code nicht in den nächsten `case` übergeht, es sei denn, man verwendet `fallthrough`. Ein weiterer Punkt ist, dass `switch` auch ohne eine Variable verwendet werden kann, was eine Überprüfung von Wahrheitswerten ermöglicht.

Ein Beispiel für die Verwendung ohne Variable:
```go
switch {
case x < 0:
    fmt.Println("x ist negativ")
case x == 0:
    fmt.Println("x ist null")
case x > 0:
    fmt.Println("x ist positiv")
}
```

## One Line Summary
Der `case` Befehl in Go ermöglicht eine klare und strukturierte Handhabung von bedingten Anweisungen innerhalb einer `switch` Anweisung zur effizienten Wertprüfung.