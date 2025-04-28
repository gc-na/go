<!--
Meta Description: # Das "continue"-Statement in Go: Effiziente Steuerung von Schleifen ## Synopsis Das `continue`-Statement in der Programmiersprache Go ermöglicht es, ...
Meta Keywords: continue, schleifen, der, ist, das
-->

# Das "continue"-Statement in Go: Effiziente Steuerung von Schleifen

## Synopsis
Das `continue`-Statement in der Programmiersprache Go ermöglicht es, den aktuellen Schleifenzyklus zu beenden und mit dem nächsten Iterationsschritt fortzufahren. Es ist ein nützliches Werkzeug zur Steuerung des Flusses innerhalb von Schleifen.

## Dokumentation
Das `continue`-Statement wird in Schleifen verwendet, um die Ausführung des aktuellen Schleifenzyklus zu unterbrechen und sofort zur nächsten Iteration überzugehen. Es kann in `for`-Schleifen eingesetzt werden, die die Hauptschleifenstruktur in Go darstellen.

### Zweck
Der Hauptzweck des `continue`-Statements ist es, bestimmte Iterationen zu überspringen, wenn eine bestimmte Bedingung erfüllt ist. Dies hilft, den Code lesbarer zu gestalten und unnötige Berechnungen in den Schleifen zu vermeiden.

### Verwendung
Das `continue`-Statement wird innerhalb einer Schleife platziert und kann optional mit einer Bedingung kombiniert werden. Es wird vor der nächsten Iteration der Schleife aufgerufen.

```go
for i := 0; i < 10; i++ {
    if i%2 == 0 { // Wenn i gerade ist
        continue // Überspringe den Rest des Schleifenzyklus
    }
    fmt.Println(i) // Gibt nur ungerade Zahlen aus
}
```

In diesem Beispiel werden nur die ungeraden Zahlen von 0 bis 9 ausgegeben, da die geraden Zahlen übersprungen werden.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung des `continue`-Statements:

### Beispiel 1: Überspringen gerader Zahlen
```go
package main

import "fmt"

func main() {
    for i := 0; i < 10; i++ {
        if i%2 == 0 {
            continue
        }
        fmt.Println(i) // Ausgabe: 1, 3, 5, 7, 9
    }
}
```

### Beispiel 2: Nutzung in geschachtelten Schleifen
```go
package main

import "fmt"

func main() {
    for i := 0; i < 3; i++ {
        for j := 0; j < 3; j++ {
            if j == 1 {
                continue // Überspringe die Iteration, wenn j gleich 1 ist
            }
            fmt.Printf("i: %d, j: %d\n", i, j)
        }
    }
}
```

## Erklärung
Ein häufiger Stolperstein beim Einsatz von `continue` ist das Missverständnis, wie es in geschachtelten Schleifen funktioniert. Das `continue`-Statement überspringt nur die aktuelle Iteration der inneren Schleife, in der es sich befindet. In geschachtelten Schleifen kann dies manchmal zu unerwarteten Ergebnissen führen, wenn man nicht genau darauf achtet, in welcher Schleife man gerade ist.

Ein weiteres wichtiges Detail ist, dass `continue` nicht mit `if`-Statements oder anderen Kontrollstrukturen außerhalb der Schleife verwendet werden kann. Es muss direkt innerhalb einer Schleife stehen, um korrekt zu funktionieren.

## Ein-Satz-Zusammenfassung
Das `continue`-Statement in Go ermöglicht es, bestimmte Iterationen in einer Schleife zu überspringen und mit der nächsten Iteration fortzufahren.