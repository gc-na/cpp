<!--
Meta Description: # C++ switch-Anweisung: Eine umfassende Anleitung ## Synopsis Die `switch`-Anweisung in C++ ermöglicht es, mehrere Bedingungen effizient zu prüfen und...
Meta Keywords: std, switch, anweisung, case, break
-->

# C++ switch-Anweisung: Eine umfassende Anleitung

## Synopsis
Die `switch`-Anweisung in C++ ermöglicht es, mehrere Bedingungen effizient zu prüfen und den Code basierend auf dem Wert einer Variablen oder eines Ausdrucks zu steuern. Sie ist eine Alternative zu einer langen Reihe von `if-else`-Anweisungen und verbessert die Lesbarkeit des Codes.

## Dokumentation
Die `switch`-Anweisung wird verwendet, um den Wert einer Variablen oder eines Ausdrucks zu überprüfen und entsprechend zu reagieren. Sie ermöglicht es Programmierern, einen Satz von möglichen Werten zu definieren, auf die der Programmfluss reagieren kann. 

### Syntax
Die grundsätzliche Syntax einer `switch`-Anweisung lautet:

```cpp
switch (ausdruck) {
    case wert1:
        // Anweisung für wert1
        break;
    case wert2:
        // Anweisung für wert2
        break;
    // weitere Fälle
    default:
        // Anweisung für alle anderen Fälle
}
```

### Zweck
Die `switch`-Anweisung ersetzt mehrere `if-else`-Anweisungen und bietet eine klarere Struktur, insbesondere wenn viele Bedingungen geprüft werden müssen. Sie kann nur mit integrierten Datentypen wie `int`, `char` oder `enum` verwendet werden.

### Verwendung
- Der Ausdruck innerhalb der `switch`-Anweisung wird einmal ausgewertet.
- Jeder `case`-Wert muss konstant und eindeutig sein.
- Ein `break`-Befehl beendet die `switch`-Anweisung; ohne `break` wird der Code in den folgenden `case`-Block weiter ausgeführt (sogenanntes "Fall durch").

## Beispiele

### Einfaches Beispiel
```cpp
#include <iostream>

int main() {
    int zahl = 2;

    switch (zahl) {
        case 1:
            std::cout << "Zahl ist 1" << std::endl;
            break;
        case 2:
            std::cout << "Zahl ist 2" << std::endl;
            break;
        case 3:
            std::cout << "Zahl ist 3" << std::endl;
            break;
        default:
            std::cout << "Zahl ist nicht 1, 2 oder 3" << std::endl;
    }

    return 0;
}
```

### Beispiel mit Fall durch
```cpp
#include <iostream>

int main() {
    char note = 'B';

    switch (note) {
        case 'A':
            std::cout << "Sehr gut!" << std::endl;
            break;
        case 'B':
        case 'C':
            std::cout << "Gut!" << std::endl; // Fall durch
            break;
        case 'D':
            std::cout << "Ausreichend!" << std::endl;
            break;
        default:
            std::cout << "Ungültige Note!" << std::endl;
    }

    return 0;
}
```

## Erklärung
Bei der Verwendung von `switch` gibt es einige häufige Fallstricke:

- **Fehlender `break`:** Wenn kein `break`-Befehl vorhanden ist, wird der Code für die nachfolgenden `case`-Anweisungen weiter ausgeführt, was zu unerwarteten Ergebnissen führen kann.
- **Typen:** Der Ausdruck in der `switch`-Anweisung muss einen ganzzahligen Datentyp oder ein `enum` sein. Gleitkommazahlen oder Strings sind nicht erlaubt.
- **Standardfall:** Ein `default`-Fall ist optional, wird jedoch empfohlen, um unerwartete Werte zu behandeln.

## Zusammenfassung
Die `switch`-Anweisung in C++ ist ein effektives Mittel zur Steuerung des Programmflusses basierend auf dem Wert von Variablen und Ausdrücken, das die Lesbarkeit und Wartbarkeit des Codes verbessert.