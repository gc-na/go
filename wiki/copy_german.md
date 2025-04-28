<!--
Meta Description: # Kopieren in Go: Effektive Datenmanipulation mit der copy-Funktion ## Synopsis Die `copy`-Funktion in Go ermöglicht es Entwicklern, Elemente von eine...
Meta Keywords: die, copy, slice, funktion, elemente
-->

# Kopieren in Go: Effektive Datenmanipulation mit der copy-Funktion

## Synopsis
Die `copy`-Funktion in Go ermöglicht es Entwicklern, Elemente von einer Slice in eine andere zu kopieren. Diese Funktion ist besonders nützlich, um Daten sicher zu duplizieren und Manipulationen an Slices durchzuführen.

## Dokumentation
Die `copy`-Funktion ist eine eingebaute Funktion in Go, die verwendet wird, um die Elemente einer Slice in eine andere Slice zu kopieren. Der Zweck dieser Funktion besteht darin, eine sichere und effiziente Möglichkeit zu bieten, Daten zwischen Slices zu übertragen.

### Verwendung
Die Syntax für die `copy`-Funktion ist wie folgt:

```go
n := copy(dst, src)
```

- `dst`: Das Ziel-Slice, in das die Elemente kopiert werden.
- `src`: Das Quell-Slice, aus dem die Elemente kopiert werden.
- `n`: Gibt die Anzahl der tatsächlich kopierten Elemente zurück. Dies entspricht der Anzahl der Elemente im kleineren Slice (entweder `dst` oder `src`).

### Details
- Die `copy`-Funktion funktioniert nur mit Slices und nicht mit Arrays oder anderen Datentypen.
- Es werden nur so viele Elemente kopiert, wie im kleineren Slice vorhanden sind.
- Wenn das Ziel-Slice kleiner ist als das Quell-Slice, werden nur die ersten `len(dst)` Elemente kopiert.

## Beispiele
Hier sind einige grundlegende Anwendungsbeispiele für die `copy`-Funktion:

### Beispiel 1: Grundlegendes Kopieren
```go
package main

import (
    "fmt"
)

func main() {
    src := []int{1, 2, 3, 4, 5}
    dst := make([]int, 3)

    n := copy(dst, src)
    fmt.Println(dst) // Ausgabe: [1 2 3]
    fmt.Println(n)   // Ausgabe: 3
}
```

### Beispiel 2: Ziel-Slice ist größer
```go
package main

import (
    "fmt"
)

func main() {
    src := []string{"Apfel", "Banane", "Kirsche"}
    dst := make([]string, 5)

    n := copy(dst, src)
    fmt.Println(dst) // Ausgabe: ["Apfel" "Banane" "Kirsche" "" ""]
    fmt.Println(n)   // Ausgabe: 3
}
```

## Erklärung
Ein häufiges Problem bei der Verwendung der `copy`-Funktion besteht darin, dass Entwickler möglicherweise annehmen, dass das Ziel-Slice immer die gleiche Größe wie das Quell-Slice haben sollte. Dies ist jedoch nicht erforderlich, da nur die Anzahl der Elemente im kleineren Slice kopiert wird. Ein weiteres häufiges Missverständnis ist, dass `copy` die Elemente des Quell-Slices nicht in den Originalzustand ändert; es handelt sich um eine flache Kopie.

Es ist wichtig zu beachten, dass `copy` keine tiefe Kopie von komplexeren Datentypen (wie Slices von Slices oder Strukturen) durchführt. In solchen Fällen müssen zusätzliche Maßnahmen ergriffen werden, um sicherzustellen, dass alle verschachtelten Daten ebenfalls kopiert werden.

## Ein-Satz-Zusammenfassung
Die `copy`-Funktion in Go ermöglicht eine effiziente und sichere Möglichkeit, Elemente zwischen Slices zu übertragen.