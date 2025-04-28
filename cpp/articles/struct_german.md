<!--
Meta Description: # C++ Struct: Eine umfassende Anleitung und Verwendung ## Synopsis In C++ ist ein `struct` eine benutzerdefinierte Datentypdefinition, die es ermöglic...
Meta Keywords: struct, und, die, structs, von
-->

# C++ Struct: Eine umfassende Anleitung und Verwendung

## Synopsis
In C++ ist ein `struct` eine benutzerdefinierte Datentypdefinition, die es ermöglicht, verschiedene Datenelemente unter einem gemeinsamen Namen zu gruppieren. Es wird häufig verwendet, um komplexe Datenstrukturen zu erstellen.

## Documentation
Ein `struct` in C++ ist eine Struktur, die es Programmierern ermöglicht, eine Sammlung von Variablen (auch als Mitglieder bezeichnet) zu definieren. Diese Mitglieder können verschiedene Datentypen haben, einschließlich primitiver Datentypen und anderer benutzerdefinierter Datentypen. 

### Zweck
Der Hauptzweck eines `struct` ist es, Daten logisch zu gruppieren, um die Verwaltung und Verwendung dieser Daten zu erleichtern. `structs` sind besonders nützlich in der objektorientierten Programmierung, wo sie als Basis für komplexere Datenstrukturen dienen können.

### Verwendung
Um ein `struct` zu definieren, verwendet man das Schlüsselwort `struct`, gefolgt von einem Namen und einer Liste von Mitgliedern innerhalb geschweifter Klammern. 

**Syntax:**
```cpp
struct StructName {
    Datentyp Mitglied1;
    Datentyp Mitglied2;
    // Weitere Mitglieder...
};
```

Nach der Definition kann ein `struct` instanziiert werden, um auf die Mitglieder zuzugreifen und sie zu manipulieren.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `struct` in C++:

### Beispiel 1: Einfache Struktur
```cpp
#include <iostream>
using namespace std;

struct Person {
    string name;
    int alter;
};

int main() {
    Person person1;
    person1.name = "Max";
    person1.alter = 25;

    cout << "Name: " << person1.name << ", Alter: " << person1.alter << endl;
    return 0;
}
```

### Beispiel 2: Struktur mit Funktionen
```cpp
#include <iostream>
using namespace std;

struct Rechteck {
    double breite;
    double hoehe;

    double berechneFlaeche() {
        return breite * hoehe;
    }
};

int main() {
    Rechteck r;
    r.breite = 5.0;
    r.hoehe = 3.0;

    cout << "Flaeche: " << r.berechneFlaeche() << endl;
    return 0;
}
```

## Erklärung
### Häufige Fallstricke und Hinweise
- **Standard-Zugriffsmodifizierer**: In `structs` sind Mitglieder standardmäßig öffentlich (`public`), im Gegensatz zu `class`, wo sie privat (`private`) sind. Dies kann zu Sicherheitsproblemen führen, wenn nicht vorsichtig damit umgegangen wird.
- **Vererbung**: `structs` können auch vererben, ähnlich wie Klassen. Der Hauptunterschied besteht jedoch darin, dass die Vererbung in `structs` standardmäßig öffentlich ist.
- **Konstruktoren und Destruktoren**: `structs` können Konstruktoren und Destruktoren definieren, um die Initialisierung und das Aufräumen von Ressourcen zu handhaben.
- **Kollisionsgefahr**: Bei der Verwendung von `structs` in großen Projekten kann es zu Namenskonflikten kommen, insbesondere wenn mehrere `structs` ähnliche oder identische Mitgliedsnamen haben.

## One Line Summary
Ein `struct` in C++ ist eine benutzerdefinierte Datentypdefinition, die es ermöglicht, verschiedene Datenelemente unter einem gemeinsamen Namen zu gruppieren und zu verwalten.