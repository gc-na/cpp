<!--
Meta Description: # Das Schlüsselwort "explicit" in C++ ## Synopsis Das Schlüsselwort `explicit` in C++ wird verwendet, um Konstruktoren und Konvertierungsoperatoren zu...
Meta Keywords: explicit, die, int, wert, beispiel
-->

# Das Schlüsselwort "explicit" in C++

## Synopsis
Das Schlüsselwort `explicit` in C++ wird verwendet, um Konstruktoren und Konvertierungsoperatoren zu kennzeichnen, die nicht implizit aufgerufen werden dürfen. Dies verhindert unbeabsichtigte Typkonvertierungen und erhöht die Typensicherheit.

## Dokumentation
Das `explicit` Schlüsselwort wird hauptsächlich in Verbindung mit Konstruktoren und Konvertierungsoperatoren eingesetzt. Durch die Verwendung von `explicit` wird sichergestellt, dass die Instanziierung eines Objekts oder die Typumwandlung nur durch eine explizite Anfrage des Programmierers erfolgt. 

### Zweck
Der Hauptzweck von `explicit` ist es, unerwünschte oder überraschende Typkonvertierungen zu verhindern, die zu schwer nachvollziehbaren Fehlern führen können. Wenn ein Konstruktor ohne `explicit` deklariert ist und einen einzelnen Parameter hat, kann dieser Konstruktor von C++ automatisch aufgerufen werden, um den Typ zu konvertieren. Dies kann in vielen Fällen zu unerwartetem Verhalten führen.

### Verwendung
Um einen Konstruktor oder einen Konvertierungsoperator als `explicit` zu deklarieren, wird das Schlüsselwort einfach vor der Definition des Konstruktors oder Operators hinzugefügt. Hier ist ein Beispiel:

```cpp
class Beispiel {
public:
    explicit Beispiel(int wert) {
        // Konstruktor-Logik
    }
};
```

In diesem Beispiel wird der Konstruktor von `Beispiel` nur dann aufgerufen, wenn ein `Beispiel`-Objekt explizit mit einem `int`-Wert erstellt wird. Ein Ausdruck wie `Beispiel obj = 5;` würde nicht funktionieren und einen Kompilierungsfehler verursachen.

## Beispiele
### Beispiel 1: Verwendung von `explicit` mit einem Konstruktor
```cpp
#include <iostream>

class Zahl {
public:
    explicit Zahl(int wert) : wert(wert) {}
    void anzeigen() const { std::cout << wert << std::endl; }
private:
    int wert;
};

int main() {
    Zahl z(10); // OK
    // Zahl z2 = 20; // Fehler: Versuch der impliziten Konvertierung
    z.anzeigen(); // Gibt 10 aus
    return 0;
}
```

### Beispiel 2: `explicit` bei Konvertierungsoperatoren
```cpp
#include <iostream>

class Prozent {
public:
    explicit Prozent(int wert) : wert(wert) {}
    operator int() const { return wert; }
private:
    int wert;
};

int main() {
    Prozent p(50);
    // int i = p; // Fehler: Versuch der impliziten Konvertierung
    int i = static_cast<int>(p); // OK: explizite Umwandlung
    std::cout << i << std::endl; // Gibt 50 aus
    return 0;
}
```

## Erklärung
Einer der häufigsten Fehler, den Programmierer machen, ist die Annahme, dass die Verwendung von Konstruktoren ohne das `explicit` Schlüsselwort immer sicher ist. Dies kann zu unerwarteten Ergebnissen führen, insbesondere wenn die Klasse in einer größeren Codebasis verwendet wird. Es ist ratsam, `explicit` für alle Konstruktoren zu verwenden, die nur einen Parameter haben, um die Möglichkeit unerwünschter Typkonvertierungen zu vermeiden.

Zusätzlich ist es wichtig zu beachten, dass `explicit` nur für Konstruktoren mit einem einzelnen Parameter und Konvertierungsoperatoren gilt. Konstruktoren mit mehreren Parametern sind nicht betroffen, da sie nicht automatisch konvertiert werden können.

## Ein-Satz-Zusammenfassung
Das `explicit` Schlüsselwort in C++ verhindert unerwünschte implizite Typkonvertierungen und erhöht die Typensicherheit, indem es sicherstellt, dass Konstruktoren und Konvertierungsoperatoren nur durch explizite Anfragen aufgerufen werden.