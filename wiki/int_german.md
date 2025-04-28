<!--
Meta Description: # Der Datentyp "int" in C++ ## Synopsis Der `int` Datentyp in C++ ist ein grundlegender Ganzzahltyp, der zur Speicherung von ganzen Zahlen verwendet w...
Meta Keywords: int, der, und, von, datentyp
-->

# Der Datentyp "int" in C++

## Synopsis
Der `int` Datentyp in C++ ist ein grundlegender Ganzzahltyp, der zur Speicherung von ganzen Zahlen verwendet wird. Er spielt eine zentrale Rolle in der Programmierung, insbesondere bei mathematischen Operationen und Schleifen.

## Dokumentation
Der `int` (Integer) Datentyp in C++ ist ein vorgegebener Datentyp, der zur Darstellung von ganzzahligen Werten dient. Er hat eine Standardgröße von 4 Bytes (32 Bit) auf den meisten Plattformen, kann jedoch je nach Architektur variieren. `int` kann sowohl positive als auch negative Werte speichern.

### Zweck
Der Hauptzweck des `int` Datentyps ist es, ganzzahlige Werte zu speichern und zu verarbeiten. Er wird häufig in Schleifen, Bedingungen und mathematischen Berechnungen verwendet.

### Verwendung
Um eine Variable vom Typ `int` zu deklarieren, verwenden Sie die folgende Syntax:

```cpp
int variableName;
```

Sie können der Variablen auch einen initialen Wert zuweisen:

```cpp
int zahl = 10;
```

### Details
- **Größen**: Der Wertebereich eines `int` reicht typischerweise von -2.147.483.648 bis 2.147.483.647.
- **Arithmetische Operationen**: `int` unterstützt alle grundlegenden arithmetischen Operationen wie Addition, Subtraktion, Multiplikation und Division.
- **Datentypen**: Es gibt auch verwandte Datentypen wie `short`, `long` und `long long`, die unterschiedliche Wertebereiche und Speichergrößen bieten.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung des `int` Datentyps:

### Beispiel 1: Deklaration und Initialisierung
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 5;
    int b = 10;
    int summe = a + b;
    
    cout << "Die Summe ist: " << summe << endl;
    return 0;
}
```

### Beispiel 2: Verwendung in einer Schleife
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "Zahl: " << i << endl;
    }
    return 0;
}
```

## Erklärung
Obwohl `int` ein sehr nützlicher Datentyp ist, gibt es einige häufige Stolpersteine:

- **Überlauf**: Wenn eine Berechnung den maximalen Wertebereich des `int` überschreitet, kann ein Überlauf auftreten, was zu unerwarteten Ergebnissen führt.
- **Typumwandlung**: Bei der Verwendung von `int` mit anderen Datentypen kann es zu unerwarteten Typumwandlungen und Verlusten von Genauigkeit kommen, insbesondere bei Gleitkommazahlen.
- **Plattformabhängigkeit**: Auf verschiedenen Plattformen kann die Größe des `int` variieren. Um eine konsistente Größe zu gewährleisten, können `int32_t` oder `int64_t` aus der `<cstdint>`-Bibliothek verwendet werden.

## Ein-Satz-Zusammenfassung
Der `int` Datentyp in C++ ist ein wesentlicher Bestandteil zur Speicherung und Manipulation von ganzen Zahlen in der Programmierung.