<!--
Meta Description: # const in C++: Verwendung und Bedeutung des Schlüsselworts ## Synopsis Das Schlüsselwort `const` in C++ dient dazu, Konstanten zu definieren, die nic...
Meta Keywords: const, kann, werden, int, und
-->

# const in C++: Verwendung und Bedeutung des Schlüsselworts

## Synopsis
Das Schlüsselwort `const` in C++ dient dazu, Konstanten zu definieren, die nicht verändert werden können. Es wird verwendet, um den Programmcode klarer, sicherer und weniger fehleranfällig zu gestalten.

## Dokumentation
### Zweck
`const` ist ein Schlüsselwort in C++, das es Entwicklern ermöglicht, Variablen und Objekte als konstant zu deklarieren. Eine Konstante kann nach ihrer Initialisierung nicht mehr modifiziert werden. Dies ist besonders nützlich, um unbeabsichtigte Änderungen an Werten zu vermeiden und den Code lesbarer zu machen.

### Verwendung
Das `const`-Schlüsselwort kann in verschiedenen Kontexten verwendet werden:

1. **Konstante Variablen**: Wenn eine Variable mit `const` deklariert wird, kann ihr Wert nach der Initialisierung nicht mehr geändert werden.
   ```cpp
   const int maxValue = 100;
   ```

2. **Konstante Zeiger**: Ein Zeiger kann konstant sein, was bedeutet, dass der Zeiger selbst nicht auf eine andere Adresse zeigen kann, aber der Wert an der Adresse, auf die er zeigt, kann geändert werden.
   ```cpp
   int value = 10;
   int* const ptr = &value; // ptr kann nicht auf eine andere Adresse zeigen
   ```

3. **Konstante Referenzen**: Eine Referenz kann als konstant deklariert werden, was bedeutet, dass der referenzierte Wert nicht geändert werden kann.
   ```cpp
   void display(const int &num) {
       // num kann hier nicht geändert werden
   }
   ```

4. **Konstanten in Klassen**: In Klassen können Methoden als konstant deklariert werden, was bedeutet, dass sie keine Änderungen an den Mitgliedsvariablen der Klasse vornehmen dürfen.
   ```cpp
   class MyClass {
   public:
       void display() const {
           // Diese Methode kann keine Mitgliedsvariablen ändern
       }
   };
   ```

### Details
- `const` kann in Kombination mit anderen Schlüsselwörtern verwendet werden, z. B. `volatile` oder `constexpr`.
- Bei der Verwendung von `const` mit Zeigern ist es wichtig, zwischen konstanten Zeigern (`int* const`) und Zeigern auf konstante Daten (`const int*`) zu unterscheiden.
- In C++11 und späteren Versionen kann `const` auch bei Lambda-Funktionen verwendet werden.

## Beispiele
```cpp
#include <iostream>

const int maxValue = 50; // Konstante Variable

int main() {
    std::cout << "Maximaler Wert: " << maxValue << std::endl;

    int value = 20;
    int* const ptr = &value; // Konstanter Zeiger
    *ptr = 25; // Erlaubt, da der Wert geändert wird
    // ptr = nullptr; // Fehler: ptr kann nicht neu zugewiesen werden

    const int &ref = value; // Konstante Referenz
    // ref = 30; // Fehler: ref kann nicht geändert werden

    return 0;
}
```

## Erklärung
Ein häufiger Fehler beim Arbeiten mit `const` ist es, zu versuchen, den Wert einer konstanten Variablen oder eines konstanten Objekts zu ändern. Dies führt zu Kompilierungsfehlern. Außerdem kann die Verwirrung zwischen konstanten Zeigern und Zeigern auf konstante Daten zu unerwartetem Verhalten führen. Es ist wichtig, die Unterschiede zu verstehen und `const` gezielt einzusetzen, um die Lesbarkeit und Wartbarkeit des Codes zu erhöhen.

## Ein Satz Zusammenfassung
Das Schlüsselwort `const` in C++ ist essentiell, um Konstanten zu definieren und sicherzustellen, dass Werte nach ihrer Initialisierung nicht mehr verändert werden können.