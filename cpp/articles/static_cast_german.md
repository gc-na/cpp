<!--
Meta Description: # statischer_cast in C++ ## Synopsis Der `static_cast` ist ein C++-Operator, der verwendet wird, um explizite Typumwandlungen zwischen kompatiblen Dat...
Meta Keywords: der, static_cast, abgeleitet, ist, basis
-->

# statischer_cast in C++

## Synopsis
Der `static_cast` ist ein C++-Operator, der verwendet wird, um explizite Typumwandlungen zwischen kompatiblen Datentypen durchzuführen. Er verbessert die Lesbarkeit des Codes und ermöglicht sichere Typkonvertierungen zur Compile-Zeit.

## Dokumentation
Der `static_cast` ist eine der vier C++-Cast-Operatoren (neben `dynamic_cast`, `const_cast` und `reinterpret_cast`). Er ermöglicht es Programmierern, zwischen verwandten Datentypen zu konvertieren, insbesondere zwischen Basisklassen und abgeleiteten Klassen sowie zwischen numerischen Typen.

### Zweck
- Sicherstellen von Typkonvertierungen, die sicher sind und zur Compile-Zeit überprüft werden.
- Erhöhen der Lesbarkeit des Codes im Vergleich zu C-Style-Casts.

### Verwendung
Der `static_cast` wird wie folgt verwendet:
```cpp
static_cast<ZielTyp>(Ausdruck);
```
Hierbei wird `Ausdruck` in den Typ `ZielTyp` konvertiert.

### Details
- Der `static_cast` kann verwendet werden, um:
  - Von einer abgeleiteten Klasse zu einer Basisklasse zu konvertieren (upcasting).
  - Von einer Basisklasse zu einer abgeleiteten Klasse zu konvertieren (downcasting), sofern der Typ tatsächlich der richtige ist (dies kann zu Laufzeitfehlern führen, wenn der Typ nicht korrekt ist).
  - Numerische Typen zu konvertieren (z.B. von `int` zu `float`).
- Bei der Verwendung von `static_cast` wird keine Laufzeitüberprüfung auf die Gültigkeit des Casts durchgeführt, was bedeutet, dass falsche Konvertierungen zu undefiniertem Verhalten führen können.

## Beispiele
### Beispiel 1: Upcasting
```cpp
class Basis {
public:
    virtual void zeige() { std::cout << "Basis" << std::endl; }
};

class Abgeleitet : public Basis {
public:
    void zeige() override { std::cout << "Abgeleitet" << std::endl; }
};

Abgeleitet abgeleitetObjekt;
Basis* basisPtr = static_cast<Basis*>(&abgeleitetObjekt);
basisPtr->zeige(); // Ausgabe: Abgeleitet
```

### Beispiel 2: Downcasting
```cpp
class Basis {
public:
    virtual void zeige() { std::cout << "Basis" << std::endl; }
};

class Abgeleitet : public Basis {
public:
    void zeige() override { std::cout << "Abgeleitet" << std::endl; }
};

Basis* basisPtr = new Abgeleitet();
Abgeleitet* abgeleitetPtr = static_cast<Abgeleitet*>(basisPtr);
abgeleitetPtr->zeige(); // Ausgabe: Abgeleitet
delete basisPtr;
```

### Beispiel 3: Numerische Typkonvertierung
```cpp
double zahl = 3.14;
int ganzzahl = static_cast<int>(zahl);
std::cout << ganzzahl; // Ausgabe: 3
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `static_cast` ist das Downcasting ohne Prüfung auf die tatsächliche Instanz. Wenn der Cast ungültig ist, führt dies zu undefiniertem Verhalten. Für sichere Downcasts sollte `dynamic_cast` verwendet werden, wenn polymorphe Typen beteiligt sind.

Ein weiteres häufiges Missverständnis ist die Annahme, dass `static_cast` immer sicher ist. Während er in vielen Fällen korrekt funktioniert, kann er in Situationen, in denen die Typen nicht kompatibel sind, zu unerwartetem Verhalten führen.

## Ein-Satz-Zusammenfassung
Der `static_cast` ist ein sicherer Mechanismus zur expliziten Typumwandlung in C++, der die Lesbarkeit verbessert und zur Compile-Zeit überprüft wird.