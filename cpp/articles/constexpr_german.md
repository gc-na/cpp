<!--
Meta Description: # constexpr in C++: Kompilierbare Konstanten und Funktionen ## Synopsis `constexpr` ist ein Schlüsselwort in C++, das es ermöglicht, Ausdrücke und Fun...
Meta Keywords: constexpr, die, zur, und, kompilierzeit
-->

# constexpr in C++: Kompilierbare Konstanten und Funktionen

## Synopsis
`constexpr` ist ein Schlüsselwort in C++, das es ermöglicht, Ausdrücke und Funktionen zur Kompilierzeit zu evaluieren, was zu einer erhöhten Effizienz und verbesserten Performance führen kann.

## Dokumentation
Das `constexpr`-Schlüsselwort wurde in C++11 eingeführt und ermöglicht es Programmierern, Variablen und Funktionen zu deklarieren, die zur Kompilierzeit ausgewertet werden können. Es dient dazu, Konstanten und Ausdrücke zu definieren, die in der Compile-Zeit berechnet werden, wodurch der Compiler Optimierungen vornehmen kann.

### Verwendung
`constexpr` kann sowohl für Variablen als auch für Funktionen verwendet werden. Eine `constexpr`-Variable wird zur Kompilierzeit initialisiert, während eine `constexpr`-Funktion nur mit `constexpr`-Argumenten aufgerufen werden kann und einen `constexpr`-Wert zurückgibt, wenn die Argumente zur Kompilierzeit bekannt sind.

#### Variablenbeispiel:
```cpp
constexpr int max_size = 100;
```

#### Funktionsbeispiel:
```cpp
constexpr int square(int x) {
    return x * x;
}
```

Funktionen, die als `constexpr` deklariert sind, können einfache Berechnungen durchführen und so zur Kompilierzeit genutzt werden.

### Details
- **Einschränkungen**: `constexpr`-Funktionen dürfen nur eine Rückgabeanweisung enthalten, die einen Wert zurückgibt. Sie können jedoch auch `if`-Anweisungen und Schleifen enthalten, solange diese zur Kompilierzeit ausgewertet werden können.
- **Kompilierzeit vs. Laufzeit**: Der Compiler entscheidet, ob der Ausdruck zur Kompilierzeit oder zur Laufzeit ausgewertet wird. Dies hängt davon ab, ob die Argumente zur Kompilierzeit bekannt sind.

## Beispiele
### Beispiel 1: Verwendung von `constexpr` für Variablen
```cpp
#include <iostream>

constexpr int num = 10;

int main() {
    std::cout << "Die Zahl ist: " << num << std::endl;
    return 0;
}
```

### Beispiel 2: Verwendung von `constexpr` zur Berechnung
```cpp
#include <iostream>

constexpr int factorial(int n) {
    return n <= 1 ? 1 : n * factorial(n - 1);
}

int main() {
    constexpr int fact_5 = factorial(5);
    std::cout << "Fakultät von 5 ist: " << fact_5 << std::endl;
    return 0;
}
```

## Erklärung
Ein häufiger Stolperstein beim Arbeiten mit `constexpr` ist das Missverständnis über die Notwendigkeit von `constexpr`-Argumenten. Wenn ein Argument zur Laufzeit berechnet wird, kann die `constexpr`-Funktion nicht zur Kompilierzeit ausgewertet werden. Zudem kann die Verwendung von `constexpr` die Lesbarkeit des Codes beeinträchtigen, wenn übermäßig komplexe Funktionen erstellt werden.

Ein weiterer Punkt ist, dass in C++20 die `constexpr`-Funktionen erheblich erweitert wurden, sodass sie nun auch komplexere Konstrukte wie dynamischen Speicher und `try-catch`-Blöcke unterstützen können.

## Ein-Satz-Zusammenfassung
`constexpr` in C++ ermöglicht die Definition von Konstanten und Funktionen, die zur Kompilierzeit ausgewertet werden, und verbessert damit die Effizienz des Codes.