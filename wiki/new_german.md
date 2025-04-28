<!--
Meta Description: # Der C++ Befehl "new": Dynamische Speicherzuweisung ## Synopsis Der `new`-Operator in C++ wird verwendet, um dynamisch Speicher für Objekte oder Arra...
Meta Keywords: new, der, operator, speicher, std
-->

# Der C++ Befehl "new": Dynamische Speicherzuweisung

## Synopsis
Der `new`-Operator in C++ wird verwendet, um dynamisch Speicher für Objekte oder Arrays während der Programmausführung zuzuweisen. Er ermöglicht eine flexible Verwaltung von Speicher und ist ein zentraler Bestandteil des C++-Speichermanagements.

## Documentation
Der `new`-Operator wird verwendet, um Speicherplatz für einen oder mehrere Objekte zur Laufzeit zu reservieren. Er gibt einen Zeiger auf den zugewiesenen Speicher zurück. Dies ist besonders nützlich, wenn die Größe der Daten zur Kompilierzeit nicht bekannt ist. 

### Verwendung
Der `new`-Operator kann für die Erstellung von Objekten und Arrays genutzt werden. Die allgemeine Syntax lautet:

- Für ein einzelnes Objekt:
  ```cpp
  Typ* zeiger = new Typ;
  ```

- Für ein Array:
  ```cpp
  Typ* zeiger = new Typ[anzahl];
  ```

### Details
- Der `new`-Operator ruft den Konstruktor des Objekts auf, um es zu initialisieren.
- Bei der Verwendung von `new` muss der Speicher mit dem `delete`-Operator freigegeben werden, um Speicherlecks zu vermeiden.
- Der `new`-Operator kann auch mit Platzhaltern wie `new (std::nothrow)` verwendet werden, um im Falle eines fehlgeschlagenen Speicherzuweisungsversuchs `nullptr` zurückzugeben, anstatt eine Ausnahme auszulösen.

## Beispiele
### Beispiel 1: Zuweisung eines einzelnen Objekts
```cpp
#include <iostream>

class Beispiel {
public:
    Beispiel() { std::cout << "Objekt erstellt." << std::endl; }
    ~Beispiel() { std::cout << "Objekt zerstört." << std::endl; }
};

int main() {
    Beispiel* obj = new Beispiel(); // Dynamische Zuweisung
    delete obj; // Freigabe des Speichers
    return 0;
}
```

### Beispiel 2: Zuweisung eines Arrays
```cpp
#include <iostream>

int main() {
    int* array = new int[5]; // Dynamische Zuweisung eines Arrays
    for (int i = 0; i < 5; ++i) {
        array[i] = i * 10;
        std::cout << array[i] << " "; // Ausgabe: 0 10 20 30 40
    }
    delete[] array; // Freigabe des Arrays
    return 0;
}
```

## Erklärung
Bei der Verwendung des `new`-Operators sollten einige häufige Fallstricke beachtet werden:

- **Speicherlecks**: Wenn der mit `new` zugewiesene Speicher nicht mit `delete` oder `delete[]` freigegeben wird, kann dies zu Speicherlecks führen, die die Leistung des Programms beeinträchtigen.
  
- **Doppelte Freigabe**: Achten Sie darauf, dass der gleiche Zeiger nicht mehrmals freigegeben wird, da dies zu undefiniertem Verhalten führen kann.

- **Nullzeiger**: Bei Verwendung von `new (std::nothrow)` sollten Sie immer auf `nullptr` prüfen, bevor Sie auf den zugewiesenen Speicher zugreifen.

## One Line Summary
Der `new`-Operator in C++ ermöglicht die dynamische Zuweisung von Speicher für Objekte und Arrays zur Laufzeit.