<!--
Meta Description: # Der "case"-Befehl in C++: Eine umfassende Anleitung ## Synopsis Der "case"-Befehl in C++ ist ein essenzieller Bestandteil der `switch`-Anweisung, di...
Meta Keywords: case, der, die, switch, break
-->

# Der "case"-Befehl in C++: Eine umfassende Anleitung

## Synopsis
Der "case"-Befehl in C++ ist ein essenzieller Bestandteil der `switch`-Anweisung, die eine effiziente Möglichkeit bietet, mehrere mögliche Ausführungspfade basierend auf dem Wert einer Variablen zu definieren.

## Dokumentation
Die `switch`-Anweisung in C++ ermöglicht es Programmierern, eine Variable zu prüfen und verschiedene Ausführungspfade zu wählen, ohne mehrere `if`-`else if`-Anweisungen verwenden zu müssen. Innerhalb der `switch`-Anweisung wird der `case`-Befehl verwendet, um spezifische Werte zu definieren, für die ein bestimmter Codeblock ausgeführt wird.

### Zweck
Der Hauptzweck des `case`-Befehls ist es, eine klare und übersichtliche Struktur für die Entscheidungsfindung in Programmen bereitzustellen, insbesondere wenn eine Variable mehrere mögliche Werte annehmen kann.

### Verwendung
Die Grundstruktur einer `switch`-Anweisung mit `case` sieht wie folgt aus:

```cpp
switch (variable) {
    case wert1:
        // Codeblock für wert1
        break;
    case wert2:
        // Codeblock für wert2
        break;
    default:
        // Codeblock, wenn keine der obigen Bedingungen zutrifft
}
```

### Details
- **Variable:** Die Variable, deren Wert überprüft wird. Sie muss einen Ganzzahltyp oder einen `enum`-Typ haben.
- **Werte (Case-Werte):** Die Werte, auf die die Variable geprüft wird. Jeder `case`-Block sollte einen einzigartigen Wert haben.
- **Break-Anweisung:** Beendet die Ausführung der `switch`-Anweisung und verhindert, dass der Code in nachfolgende `case`-Blöcke fortgesetzt wird.
- **Default:** Ein optionaler Block, der ausgeführt wird, wenn keiner der `case`-Werte zutrifft.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung des `case`-Befehls in C++:

### Beispiel 1: Einfache Verwendung

```cpp
#include <iostream>
using namespace std;

int main() {
    int tag = 3;

    switch (tag) {
        case 1:
            cout << "Montag";
            break;
        case 2:
            cout << "Dienstag";
            break;
        case 3:
            cout << "Mittwoch";
            break;
        default:
            cout << "Ungültiger Tag";
    }

    return 0;
}
```

### Beispiel 2: Mehrere `case`-Anweisungen

```cpp
#include <iostream>
using namespace std;

int main() {
    char note = 'B';

    switch (note) {
        case 'A':
        case 'B':
            cout << "Gut!";
            break;
        case 'C':
            cout << "Befriedigend!";
            break;
        default:
            cout << "Ungenügend!";
    }

    return 0;
}
```

## Erklärung
Ein häufiger Fallstrick bei der Verwendung des `case`-Befehls ist das Vergessen der `break`-Anweisung. Wenn diese weggelassen wird, wird der Code im nächsten `case`-Block ebenfalls ausgeführt (sogenanntes "fall-through"). Das kann zu unerwartetem Verhalten führen. 

Ein weiterer Punkt ist, dass die Werte in jedem `case`-Block eindeutig sein müssen; das bedeutet, dass zwei `case`-Anweisungen nicht denselben Wert haben dürfen. 

Zusätzlich ist es wichtig zu beachten, dass der `switch`-Befehl nur für Ganzzahltypen und `enum`-Typen verwendet werden kann. Bei Zeichenfolgen oder anderen Datentypen muss auf alternative Entscheidungsstrukturen zurückgegriffen werden.

## Einzeilige Zusammenfassung
Der `case`-Befehl in C++ ermöglicht die effiziente Handhabung mehrerer Ausführungspfade innerhalb einer `switch`-Anweisung.