<!--
Meta Description: # Virtuelle Funktionen in C++: Ein Leitfaden für objektorientierte Programmierung ## Synopsis In C++ sind virtuelle Funktionen ein zentrales Konzept d...
Meta Keywords: der, funktionen, die, wird, das
-->

# Virtuelle Funktionen in C++: Ein Leitfaden für objektorientierte Programmierung

## Synopsis
In C++ sind virtuelle Funktionen ein zentrales Konzept der objektorientierten Programmierung, das es ermöglicht, die Methode einer Basisklasse in abgeleiteten Klassen zu überschreiben und polymorphe Verhaltensweisen zu implementieren.

## Dokumentation
### Zweck
Virtuelle Funktionen ermöglichen es C++-Programmierern, dynamisches Polymorphismus zu implementieren. Das bedeutet, dass die Methode, die zur Laufzeit aufgerufen wird, basierend auf dem tatsächlichen Typ des Objekts bestimmt wird, nicht auf dem Typ des Zeigers oder der Referenz, die auf das Objekt verweist.

### Verwendung
Um eine Funktion als virtuell zu kennzeichnen, wird das Schlüsselwort `virtual` vor der Funktionsdeklaration in der Basisklasse verwendet. In abgeleiteten Klassen können diese Funktionen überschrieben werden, um spezifisches Verhalten zu implementieren.

### Details
- **Syntax**: 
  ```cpp
  class Basisklasse {
  public:
      virtual void virtuelleFunktion();
  };
  
  class AbgeleiteteKlasse : public Basisklasse {
  public:
      void virtuelleFunktion() override; // override ist optional, empfiehlt sich aber
  };
  ```
- **Destruktoren**: Es ist gute Praxis, Destruktoren in Basisklassen als virtuell zu deklarieren, um sicherzustellen, dass der richtige Destruktor aufgerufen wird, wenn Objekte über einen Basisklassenzeiger gelöscht werden.
- **Leistung**: Der Aufruf virtueller Funktionen ist etwas langsamer als der von nicht-virtuellen Funktionen, da er einen zusätzlichen Overhead für die dynamische Bindung hat.

## Beispiele
```cpp
#include <iostream>
using namespace std;

class Tier {
public:
    virtual void geräuschMachen() {
        cout << "Das Tier macht ein Geräusch" << endl;
    }
};

class Hund : public Tier {
public:
    void geräuschMachen() override {
        cout << "Der Hund bellt" << endl;
    }
};

int main() {
    Tier* tier = new Hund();
    tier->geräuschMachen(); // Gibt "Der Hund bellt" aus
    delete tier;
    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **Vergessen, `virtual` zu verwenden**: Wenn ein Entwickler vergisst, das Schlüsselwort `virtual` in der Basisklasse zu verwenden, wird die Methode nicht polymorph und die abgeleitete Methode wird nicht aufgerufen.
- **Unsichtbare virtuelle Funktionen**: Wenn eine virtuelle Funktion nicht in der abgeleiteten Klasse überschrieben wird, wird die Funktion der Basisklasse aufgerufen, was manchmal unerwartete Ergebnisse liefert.
- **Kopieren von Objekten**: Bei der Verwendung von virtuellen Funktionen kann das Kopieren von Objekten zu unerwartetem Verhalten führen, besonders wenn Zeiger oder Referenzen verwendet werden.

## Ein-Satz-Zusammenfassung
Virtuelle Funktionen in C++ ermöglichen dynamisches Polymorphismus, indem sie die Überschreibung von Methoden in abgeleiteten Klassen unterstützen.