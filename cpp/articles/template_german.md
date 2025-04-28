<!--
Meta Description: # C++ Templates: Eine umfassende Anleitung ## Synopsis Templates in C++ ermöglichen die Erstellung von generischem Code, der für verschiedene Datentyp...
Meta Keywords: die, templates, value, std, template
-->

# C++ Templates: Eine umfassende Anleitung

## Synopsis
Templates in C++ ermöglichen die Erstellung von generischem Code, der für verschiedene Datentypen verwendet werden kann, ohne den Code für jeden Typen neu zu schreiben.

## Dokumentation
### Zweck
Templates sind ein zentrales Merkmal von C++, das es Entwicklern ermöglicht, Funktionen und Klassen zu definieren, die mit jedem Datentyp arbeiten können. Dies fördert die Wiederverwendbarkeit des Codes und erleichtert die Wartung.

### Verwendung
Templates können sowohl für Funktionen als auch für Klassen erstellt werden. Dabei wird der Datentyp als Parameter übergeben. C++ unterscheidet zwischen zwei Haupttypen von Templates:

1. **Funktionstemplates**: Erlauben die Definition von Funktionen, die mit verschiedenen Datentypen arbeiten.
2. **Klassen-Templates**: Erlauben die Definition von Klassen, die generisch sind und mit unterschiedlichen Datentypen instanziiert werden können.

### Details
Ein einfaches Beispiel für ein Funktionstemplate könnte so aussehen:

```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}
```

Hier wird `T` als Platzhalter für einen Datentyp verwendet, der bei der Verwendung des Templates durch einen konkreten Typ ersetzt wird.

Klassen-Templates werden ähnlich deklariert:

```cpp
template <typename T>
class Box {
public:
    Box(T value) : value(value) {}
    T getValue() const { return value; }
private:
    T value;
};
```

## Beispiele
### Funktionstemplate Beispiel
```cpp
#include <iostream>

template <typename T>
T add(T a, T b) {
    return a + b;
}

int main() {
    std::cout << add(5, 3) << std::endl; // gibt 8 aus
    std::cout << add(5.5, 2.5) << std::endl; // gibt 8.0 aus
    return 0;
}
```

### Klassen-Template Beispiel
```cpp
#include <iostream>

template <typename T>
class Box {
public:
    Box(T value) : value(value) {}
    T getValue() const { return value; }
private:
    T value;
};

int main() {
    Box<int> intBox(123);
    Box<std::string> strBox("Hallo");
    
    std::cout << intBox.getValue() << std::endl; // gibt 123 aus
    std::cout << strBox.getValue() << std::endl; // gibt "Hallo" aus
    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **Typenkonflikte**: Wenn Sie ein Template mit inkompatiblen Datentypen verwenden, kann dies zu Kompilierungsfehlern führen.
- **Spezialisierungen**: Manchmal kann es notwendig sein, spezielle Implementierungen für bestimmte Datentypen zu definieren, was als Template-Spezialisierung bezeichnet wird.
- **Fehlende Typen**: Wenn ein Template nicht mit einem Typen verwendet wird, der die erwarteten Operationen unterstützt, wird ein Fehler zur Kompilierzeit auftreten.

### Zusätzliche Hinweise
- Templates können auch mit nicht-typ-basierten Parametern (wie nicht typisierten Parametern) verwendet werden, was zusätzliche Flexibilität bietet.
- Es ist wichtig, die Verwendung von `typename` und `class` zu verstehen, da sie in vielen Fällen austauschbar sind, jedoch in spezifischen Kontexten unterschiedliche Bedeutungen haben können.

## Ein-Satz-Zusammenfassung
Templates in C++ ermöglichen die Erstellung von flexiblem, generischem Code, der mit verschiedenen Datentypen arbeiten kann.