<!--
Meta Description: # Rückgabewert in Go: Verständnis und Anwendung des "return"-Statements ## Synopsis Das "return"-Statement in Go ermöglicht es Programmierern, Werte a...
Meta Keywords: return, funktion, statement, die, rückgabewert
-->

# Rückgabewert in Go: Verständnis und Anwendung des "return"-Statements

## Synopsis
Das "return"-Statement in Go ermöglicht es Programmierern, Werte aus Funktionen zurückzugeben. Es ist ein essenzielles Element der Funktionsdefinition und -verwendung in der Programmiersprache Go.

## Dokumentation
In Go wird das "return"-Statement verwendet, um den Fluss der Ausführung einer Funktion zu steuern, indem es den aktuellen Funktionskontext verlässt und optionale Werte zurückgibt. Es ist wichtig, dass die Rückgabewerte mit den in der Funktionsdefinition angegebenen Rückgabetypen übereinstimmen.

### Zweck
Das "return"-Statement ist entscheidend, um Daten von einer Funktion an den Aufrufer zurückzugeben, was die Modularität und Wiederverwendbarkeit des Codes fördert.

### Verwendung
Um das "return"-Statement zu verwenden, definieren Sie zunächst eine Funktion mit Rückgabewerten. Das "return"-Statement wird dann innerhalb der Funktion verwendet, um die Rückgabewerte anzugeben. Hier ist die allgemeine Syntax:

```go
func FunktionName(parameterTypen) (rückgabewertTypen) {
    // Funktionale Logik
    return rückgabewerte
}
```

### Details
- Eine Funktion kann mehrere Rückgabewerte haben.
- Es ist möglich, eine Funktion ohne Rückgabewert zu definieren; in diesem Fall kann das "return"-Statement leer sein.
- Wenn die Funktion einen Rückgabewert hat, müssen alle Ausführungspfade der Funktion ein "return"-Statement erreichen, es sei denn, die Funktion hat einen leeren Rückgabewert.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung des "return"-Statements in Go:

### Beispiel 1: Einfache Funktion mit einem Rückgabewert
```go
package main

import "fmt"

func addiere(x int, y int) int {
    return x + y
}

func main() {
    ergebnis := addiere(3, 4)
    fmt.Println(ergebnis) // Ausgabe: 7
}
```

### Beispiel 2: Funktion mit mehreren Rückgabewerten
```go
package main

import "fmt"

func teile(x int, y int) (int, error) {
    if y == 0 {
        return 0, fmt.Errorf("Division durch Null")
    }
    return x / y, nil
}

func main() {
    ergebnis, err := teile(10, 2)
    if err != nil {
        fmt.Println(err)
    } else {
        fmt.Println(ergebnis) // Ausgabe: 5
    }
}
```

### Beispiel 3: Funktion ohne Rückgabewert
```go
package main

import "fmt"

func begruessung(name string) {
    fmt.Printf("Hallo, %s!\n", name)
}

func main() {
    begruessung("Max") // Ausgabe: Hallo, Max!
}
```

## Erklärung
Ein häufiger Fehler, den Entwickler machen, ist, das "return"-Statement in einer Funktion zu vergessen, die einen Rückgabewert hat. Dies führt zu einem Kompilierungsfehler. Ein weiteres Problem kann auftreten, wenn die Rückgabewerte nicht mit den deklarierten Typen übereinstimmen, was ebenfalls zu einem Fehler führt. Es ist wichtig, den Rückgabewert im Hauptprogramm oder der aufrufenden Funktion ordnungsgemäß zu verarbeiten, insbesondere wenn Fehler zurückgegeben werden.

## Ein-Satz-Zusammenfassung
Das "return"-Statement in Go ermöglicht es, Werte aus Funktionen zurückzugeben und den Fluss der Programmausführung zu steuern.