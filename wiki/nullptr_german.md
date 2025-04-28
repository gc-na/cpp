<!--
Meta Description: # nullptr in C++: Der moderne Nullzeiger ## Synopsis `nullptr` ist ein Schlüsselwort in C++, das ab C++11 eingeführt wurde, um einen Typ-sicheren Null...
Meta Keywords: nullptr, die, null, der, ist
-->

# nullptr in C++: Der moderne Nullzeiger

## Synopsis
`nullptr` ist ein Schlüsselwort in C++, das ab C++11 eingeführt wurde, um einen Typ-sicheren Nullzeiger darzustellen. Es ersetzt die Verwendung von `NULL` und verbessert die Lesbarkeit sowie die Sicherheit von Zeigeroperationen.

## Documentation
`nullptr` ist ein spezielles Literal, das den Typ `std::nullptr_t` besitzt. Es dient als Nullwert für Zeiger und wird häufig in Situationen verwendet, in denen ein Zeiger initialisiert oder auf einen null-Wert gesetzt werden soll. 

### Zweck
Der Hauptzweck von `nullptr` ist es, eine eindeutige und typsichere Art der Nullzeiger-Darstellung zu bieten, die Ambiguitäten, die mit der Verwendung von `NULL` verbunden sind, vermeidet. `nullptr` kann sowohl für rohe Zeiger als auch für smart pointers verwendet werden, was die Verwendung in modernen C++-Programmen erleichtert.

### Verwendung
Um `nullptr` zu verwenden, muss kein Header eingebunden werden, da es Teil der C++-Sprache selbst ist. Der Code verwendet `nullptr` wie folgt:

```cpp
int* ptr = nullptr; // Initialisierung eines Zeigers auf null
```

### Details
- `nullptr` ist typensicher und löst Überladungsprobleme, die auftreten können, wenn man `NULL` verwendet. Beispielsweise kann `NULL` sowohl als Nullzeiger als auch als Integer interpretiert werden, was zu unerwarteten Ergebnissen führen kann.
- `nullptr` kann in Funktionsaufrufen verwendet werden, um sicherzustellen, dass der richtige Funktionsüberladungsmechanismus aktiviert wird.

## Examples
Hier sind einige grundlegende Beispiele, die die Verwendung von `nullptr` veranschaulichen:

### Beispiel 1: Initialisierung eines Zeigers
```cpp
int* p = nullptr; // p ist ein Zeiger, der auf nichts zeigt
```

### Beispiel 2: Überprüfung auf null
```cpp
if (p == nullptr) {
    std::cout << "Der Zeiger zeigt auf null." << std::endl;
}
```

### Beispiel 3: Verwendung in Funktionen
```cpp
void func(int* ptr) {
    if (ptr == nullptr) {
        std::cout << "Der übergebene Zeiger ist null." << std::endl;
    }
}

func(nullptr); // Aufruf der Funktion mit nullptr
```

## Explanation
### Häufige Fallstricke
- **Verwechslung mit NULL**: Es ist wichtig, `nullptr` nicht mit `NULL` zu verwechseln, da `NULL` je nach Kontext unterschiedliche Typen annehmen kann.
- **Typüberladung**: Bei der Verwendung von Funktionen, die überladen sind, kann `nullptr` dazu beitragen, die richtige Funktion zu wählen, während `NULL` dies möglicherweise nicht tut.

### Zusätzliche Hinweise
- `nullptr` ist nicht nur für rohe Zeiger geeignet, sondern funktioniert auch gut mit smart pointers wie `std::shared_ptr` und `std::unique_ptr`.
- Die Verwendung von `nullptr` ist eine bewährte Methode und sollte in neuem C++-Code bevorzugt werden.

## One Line Summary
`nullptr` ist das moderne, typsichere Nullzeiger-Literal in C++, das die Verwendung von Zeigern sicherer und klarer macht.