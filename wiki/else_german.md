<!--
Meta Description: # Der "else"-Befehl in C++: Bedingte Anweisungen einfach erklärt ## Synopsis Der "else"-Befehl in C++ ermöglicht es Programmierern, alternative Anweis...
Meta Keywords: else, der, ist, befehl, anweisungen
-->

# Der "else"-Befehl in C++: Bedingte Anweisungen einfach erklärt

## Synopsis
Der "else"-Befehl in C++ ermöglicht es Programmierern, alternative Anweisungen auszuführen, wenn eine Bedingung in einer "if"-Anweisung nicht erfüllt ist. Dies ist ein grundlegendes Konzept zur Steuerung des Programmflusses.

## Dokumentation
Der "else"-Befehl wird in Verbindung mit der "if"-Anweisung verwendet, um Bedingungen zu überprüfen und alternative Codepfade zu definieren. Die allgemeine Syntax für die Verwendung von "if" und "else" ist wie folgt:

```cpp
if (Bedingung) {
    // Anweisungen, wenn die Bedingung wahr ist
} else {
    // Anweisungen, wenn die Bedingung falsch ist
}
```

### Zweck
Der Hauptzweck des "else"-Befehls ist es, eine Entscheidungsstruktur zu schaffen, die es einem Programm ermöglicht, unterschiedliche Aktionen basierend auf bestimmten Bedingungen auszuführen.

### Verwendung
Der "else"-Befehl kann auch in Kombination mit "else if" verwendet werden, um mehrere Bedingungen zu überprüfen:

```cpp
if (Bedingung1) {
    // Anweisungen für Bedingung1
} else if (Bedingung2) {
    // Anweisungen für Bedingung2
} else {
    // Anweisungen, wenn keine der Bedingungen erfüllt ist
}
```

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung von "else":

### Beispiel 1: Einfacher "if-else"-Befehl

```cpp
#include <iostream>
using namespace std;

int main() {
    int zahl = 10;

    if (zahl > 5) {
        cout << "Die Zahl ist größer als 5." << endl;
    } else {
        cout << "Die Zahl ist 5 oder kleiner." << endl;
    }

    return 0;
}
```

### Beispiel 2: Verwendung von "else if"

```cpp
#include <iostream>
using namespace std;

int main() {
    int note = 85;

    if (note >= 90) {
        cout << "Sehr gut" << endl;
    } else if (note >= 80) {
        cout << "Gut" << endl;
    } else {
        cout << "Verbesserungsbedarf" << endl;
    }

    return 0;
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung des "else"-Befehls ist das Vergessen von geschweiften Klammern (`{}`), insbesondere wenn nur eine Anweisung folgt. In solchen Fällen kann der Code schwerer lesbar werden, und es besteht die Gefahr, dass bei späteren Änderungen Fehler auftreten. Daher ist es eine gute Praxis, immer geschweifte Klammern zu verwenden, auch wenn nur eine einzelne Anweisung existiert.

### Weitere Hinweise
- Der "else"-Befehl kann nur einmal pro "if"-Block verwendet werden. Wenn mehrere alternative Bedingungen erforderlich sind, sollten "else if"-Anweisungen verwendet werden.
- Der "else"-Befehl kann nicht ohne vorhergehende "if"-Anweisung stehen.

## Ein-Satz-Zusammenfassung
Der "else"-Befehl in C++ ermöglicht es, alternative Codepfade basierend auf der Evaluierung von Bedingungen zu definieren.