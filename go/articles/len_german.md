<!--
Meta Description: # len in Go: Die Länge von Arrays, Slices, Strings und Maps bestimmen ## Synopsis Die `len`-Funktion in Go ist ein integrierter Befehl, der verwendet ...
Meta Keywords: der, die, länge, len, anzahl
-->

# len in Go: Die Länge von Arrays, Slices, Strings und Maps bestimmen

## Synopsis
Die `len`-Funktion in Go ist ein integrierter Befehl, der verwendet wird, um die Länge von verschiedenen Datentypen wie Arrays, Slices, Strings und Maps zu ermitteln.

## Documentation
Die `len`-Funktion ist eine grundlegende Funktion in Go, die es Entwicklern ermöglicht, die Anzahl der Elemente in einem gegebenen Datentyp schnell und effizient zu bestimmen. Sie ist ein Teil der Standardbibliothek und kann auf die folgenden Datentypen angewendet werden:

- **Arrays**: Gibt die Anzahl der Elemente im Array zurück.
- **Slices**: Gibt die Anzahl der Elemente im Slice zurück.
- **Strings**: Gibt die Anzahl der Zeichen im String zurück (in Bytes).
- **Maps**: Gibt die Anzahl der Schlüssel-Wert-Paare in der Map zurück.

### Syntax
```go
len(v interface{}) int
```

### Parameter
- `v`: Kann ein Array, Slice, String oder eine Map sein.

### Rückgabewert
- Gibt einen `int` zurück, der die Anzahl der vorhandenen Elemente, Zeichen oder Schlüssel-Werte repräsentiert.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung der `len`-Funktion:

### Beispiel 1: Länge eines Arrays
```go
package main

import "fmt"

func main() {
    arr := [3]int{1, 2, 3}
    fmt.Println("Länge des Arrays:", len(arr)) // Ausgabe: Länge des Arrays: 3
}
```

### Beispiel 2: Länge eines Slices
```go
package main

import "fmt"

func main() {
    slice := []string{"Go", "Python", "Java"}
    fmt.Println("Länge des Slices:", len(slice)) // Ausgabe: Länge des Slices: 3
}
```

### Beispiel 3: Länge eines Strings
```go
package main

import "fmt"

func main() {
    str := "Hallo, Welt!"
    fmt.Println("Länge des Strings:", len(str)) // Ausgabe: Länge des Strings: 13
}
```

### Beispiel 4: Länge einer Map
```go
package main

import "fmt"

func main() {
    m := map[string]int{"eins": 1, "zwei": 2}
    fmt.Println("Anzahl der Einträge in der Map:", len(m)) // Ausgabe: Anzahl der Einträge in der Map: 2
}
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von `len` in Go ist, dass die Länge von Strings in Bytes und nicht in Zeichen zurückgegeben wird. Wenn ein String mehrbyte Zeichen (wie UTF-8) enthält, kann die zurückgegebene Länge von der erwarteten Anzahl der Zeichen abweichen. Es ist wichtig, dies zu berücksichtigen, wenn mit mehrbyte Zeichen gearbeitet wird.

Außerdem funktioniert `len` nicht mit `nil`-Slices oder -Maps. Der Aufruf von `len` auf einem `nil`-Slice oder einer `nil`-Map gibt `0` zurück, was in den meisten Fällen das erwartete Verhalten ist, aber Entwickler sollten darauf achten, um unbeabsichtigte Logikfehler zu vermeiden.

## One Line Summary
Die `len`-Funktion in Go bestimmt die Länge von Arrays, Slices, Strings und Maps und gibt die Anzahl der Elemente, Zeichen oder Schlüssel-Werte zurück.