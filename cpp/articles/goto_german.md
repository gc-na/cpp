<!--
Meta Description: # goto in C++: Verwendung, Beispiele und Fallstricke ## Synopsis Der `goto`-Befehl in C++ ermöglicht es Programmierern, den Programmfluss an eine best...
Meta Keywords: goto, die, label, kann, ein
-->

# goto in C++: Verwendung, Beispiele und Fallstricke

## Synopsis
Der `goto`-Befehl in C++ ermöglicht es Programmierern, den Programmfluss an eine bestimmte Stelle im Code zu springen. Obwohl er oft als schlecht angesehen wird, kann er in bestimmten Szenarien nützlich sein.

## Dokumentation
Der `goto`-Befehl ist eine Steueranweisung in C++, die es ermöglicht, die Ausführung des Programms zu einem markierten Label zu springen. Ein Label wird durch einen Bezeichner gefolgt von einem Doppelpunkt definiert. Der Hauptzweck von `goto` ist es, den Fluss des Codes zu steuern, insbesondere in komplexen Kontrollstrukturen.

### Verwendung
Die Syntax für `goto` ist wie folgt:
```cpp
goto label;
```
Ein Label wird definiert als:
```cpp
label:
```

### Details
- **Sichtbarkeit**: Labels sind im Gültigkeitsbereich des umgebenden Blocks sichtbar.
- **Sprungziel**: Ein `goto`-Sprung kann nur innerhalb des gleichen Funktionsbereichs erfolgen. Ein Sprung zu einem Label in einer anderen Funktion ist nicht erlaubt.
- **Codequalität**: Der übermäßige Gebrauch von `goto` kann zu unübersichtlichem und schwer wartbarem Code führen. Aus diesem Grund wird es oft als Anti-Pattern betrachtet.

## Beispiele
Hier sind einige einfache Beispiele, die die Verwendung von `goto` veranschaulichen:

### Beispiel 1: Einfaches Label und Sprung
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Vor dem Sprung." << endl;
    goto jumpLabel;
    cout << "Dieser Teil wird übersprungen." << endl;

jumpLabel:
    cout << "Nach dem Sprung." << endl;
    return 0;
}
```

### Beispiel 2: Verwendung in einer Schleife
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;

    loop:
    if (i < 5) {
        cout << "Zahl: " << i << endl;
        i++;
        goto loop; // Zurück zum Label
    }

    return 0;
}
```

## Erklärung
Obwohl `goto` in bestimmten Situationen nützlich sein kann, gibt es mehrere Fallstricke, die Entwickler beachten sollten:

1. **Codequalität**: Übermäßige Verwendung von `goto` kann den Code schwer verständlich machen. Dies kann zu Fehlern führen und die Wartbarkeit verringern.
2. **Sprung über Variablen**: Ein `goto`-Sprung kann dazu führen, dass Variablen nicht initialisiert werden, was zu undefiniertem Verhalten führt.
3. **Verwirrung im Fluss**: Die Verwendung von `goto` kann den logischen Fluss des Codes stören, was das Debuggen erschwert.

Im Allgemeinen sollte `goto` nur in Ausnahmefällen und mit Bedacht eingesetzt werden.

## Ein Satz Zusammenfassung
Der `goto`-Befehl in C++ ermöglicht es, den Programmfluss an ein bestimmtes Label zu springen, sollte jedoch sparsam und mit Vorsicht verwendet werden, um die Codequalität zu gewährleisten.