<!--
Meta Description: # C++ "throw": Fehlerbehandlung und Ausnahmeverwaltung ## Synopsis In C++ wird das Schlüsselwort `throw` verwendet, um Ausnahmen zu werfen und die Feh...
Meta Keywords: std, throw, ausnahmen, die, ausnahme
-->

# C++ "throw": Fehlerbehandlung und Ausnahmeverwaltung

## Synopsis
In C++ wird das Schlüsselwort `throw` verwendet, um Ausnahmen zu werfen und die Fehlerbehandlung in Programmen zu erleichtern. Es ermöglicht Entwicklern, unerwartete Ereignisse zu signalisieren und deren Behandlung durch geeignete `catch`-Blöcke zu ermöglichen.

## Dokumentation
### Zweck
Der Befehl `throw` dient dazu, eine Ausnahme auszulösen, die dann von einem entsprechenden `catch`-Block behandelt werden kann. Dies ist ein zentraler Bestandteil des C++-Ausnahmehandlings, das eine strukturierte Möglichkeit bietet, mit Fehlern und unerwartetem Verhalten umzugehen.

### Verwendung
Um `throw` zu verwenden, müssen Sie eine Ausnahmebedingung definieren, die Sie auslösen möchten. Dies kann ein Standardausnahmeobjekt oder ein benutzerdefiniertes Objekt sein. Der allgemeine Syntax lautet:

```cpp
throw Ausdruck;
```

Hierbei ist `Ausdruck` der Wert oder das Objekt, das geworfen wird. Nach dem `throw`-Befehl wird die Kontrollflussausführung zu dem nächsten passenden `catch`-Block übergeben.

### Details
- **Ausnahmen**: C++ bietet eine Hierarchie von Standardausnahmen wie `std::runtime_error`, `std::logic_error` usw. Benutzerdefinierte Ausnahmen können durch Ableiten von `std::exception` erstellt werden.
- **Ausnahmebehandlung**: Nach dem Auslösen einer Ausnahme wird der Stack zurückgegangen, bis ein passender `catch`-Block gefunden wird, der die Ausnahme behandelt.
- **Ressourcenverwaltung**: Es ist wichtig, Ressourcen wie Speicher oder Dateihandles in einem `try`-Block oder durch RAII (Resource Acquisition Is Initialization) zu verwalten, um Speicherlecks zu vermeiden.

## Beispiele

### Einfaches Beispiel
```cpp
#include <iostream>
#include <stdexcept>

void testThrow() {
    throw std::runtime_error("Ein Fehler ist aufgetreten!");
}

int main() {
    try {
        testThrow();
    } catch (const std::runtime_error& e) {
        std::cout << "Ausnahme gefangen: " << e.what() << std::endl;
    }
    return 0;
}
```

### Benutzerdefinierte Ausnahme
```cpp
#include <iostream>
#include <exception>

class MeineAusnahme : public std::exception {
public:
    const char* what() const noexcept override {
        return "Benutzerdefinierte Ausnahme";
    }
};

void testBenutzerdefinierteAusnahme() {
    throw MeineAusnahme();
}

int main() {
    try {
        testBenutzerdefinierteAusnahme();
    } catch (const MeineAusnahme& e) {
        std::cout << "Ausnahme gefangen: " << e.what() << std::endl;
    }
    return 0;
}
```

## Erklärung
### Häufige Fallstricke
- **Unbehandelte Ausnahmen**: Wenn eine Ausnahme nicht gefangen wird, führt dies zu einem Programmabbruch.
- **Ressourcenlecks**: Wenn eine Ausnahme innerhalb von Ressourcenverwaltung (z.B. dynamischer Speicher) auftritt und diese nicht richtig behandelt wird, können Speicherlecks entstehen.
- **Nicht Standardisierte Ausnahmen**: Es ist ratsam, Standardausnahmen zu verwenden oder eigene Ausnahmen von `std::exception` abzuleiten, um die Kompatibilität und Lesbarkeit zu gewährleisten.

### Zusätzliche Hinweise
- C++ erlaubt das Werfen von beliebigen Objekten, es ist jedoch gängige Praxis, Ausnahmen zu verwenden, die von `std::exception` abgeleitet sind.
- Eine gute Programmierpraxis besteht darin, Ausnahmen so spezifisch wie möglich zu gestalten, um die Fehlerdiagnose zu erleichtern.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort `throw` in C++ ermöglicht die Auslösung von Ausnahmen zur strukturierten Fehlerbehandlung in Programmen.