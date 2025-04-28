<!--
Meta Description: # Verwendung von typeid in C++ ## Synopsis Der `typeid` Operator in C++ ermöglicht die Ermittlung des Typs eines Ausdrucks zur Laufzeit. Er ist ein wi...
Meta Keywords: typeid, der, typ, von, den
-->

# Verwendung von typeid in C++

## Synopsis
Der `typeid` Operator in C++ ermöglicht die Ermittlung des Typs eines Ausdrucks zur Laufzeit. Er ist ein wichtiges Werkzeug in der Typidentifikation, insbesondere in der Arbeit mit polymorphen Klassen und der RTTI (Runtime Type Information).

## Dokumentation
Der `typeid` Operator gehört zur C++-Standardbibliothek und wird verwendet, um Informationen über den Typ eines Objekts oder einer Referenz zur Laufzeit zu erhalten. Er kann auf jede Art von Ausdruck angewendet werden, und das Ergebnis ist ein Objekt des Typs `std::type_info`, das Informationen über den Typ enthält.

### Verwendung
Die Syntax für die Verwendung von `typeid` ist wie folgt:

```cpp
#include <typeinfo>

const std::type_info& type_info = typeid(expression);
```

Hierbei ist `expression` der Ausdruck, dessen Typ ermittelt werden soll. Wenn der Typ polymorph ist, gibt `typeid` den dynamischen Typ des Objekts zurück.

### Details
- **RTTI**: `typeid` ist ein Bestandteil der RTTI in C++, die es ermöglicht, Informationen über Typen zur Laufzeit zu erhalten.
- **Polymorphe Typen**: Bei polymorphen Typen gibt `typeid` den dynamischen Typ des Objekts zurück, während es bei nicht-polymorphen Typen den statischen Typ zurückgibt.
- **Vergleich von Typen**: Das `std::type_info`-Objekt bietet die Methode `name()`, die den Namen des Typs als `const char*` zurückgibt. Der Vergleich von Typen kann durch die Verwendung der `==`-Operator über `std::type_info`-Objekte erfolgen.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `typeid`:

```cpp
#include <iostream>
#include <typeinfo>

class Base {
    virtual void func() {}
};

class Derived : public Base {};

int main() {
    Base b;
    Derived d;

    std::cout << "Typ von b: " << typeid(b).name() << std::endl; // gibt den statischen Typ zurück
    std::cout << "Typ von d: " << typeid(d).name() << std::endl; // gibt den statischen Typ zurück
    Base* ptr = &d;
    std::cout << "Dynamischer Typ von ptr: " << typeid(*ptr).name() << std::endl; // gibt den dynamischen Typ zurück
    return 0;
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `typeid` tritt auf, wenn man den Operator auf ein nicht-polymorphes Objekt anwendet. In solchen Fällen wird immer der statische Typ zurückgegeben, was zu Verwirrung führen kann. Darüber hinaus kann `typeid` nicht auf uninitialisierte oder null-Zeiger angewendet werden, da dies zu einem Laufzeitfehler führt.

### Zusätzliche Hinweise
- Der `typeid` Operator ist nicht immer portabel, da die Rückgabewerte von `name()` von Compiler zu Compiler unterschiedlich sein können.
- Bei der Verwendung von `typeid` in Vorlagen oder generischen Programmierungen sollte man vorsichtig sein, da der Typ in diesen Kontexten möglicherweise nicht wie erwartet erkannt wird.

## Ein-Satz-Zusammenfassung
Der `typeid` Operator in C++ ermöglicht die dynamische Typidentifikation eines Ausdrucks zur Laufzeit, insbesondere bei polymorphen Klassen.