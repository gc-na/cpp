<!--
Meta Description: # C++ extern: Verwendung und Bedeutung ## Synopsis Das Schlüsselwort `extern` in C++ dient zur Deklaration von Variablen und Funktionen, die in andere...
Meta Keywords: die, extern, der, von, variable
-->

# C++ extern: Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort `extern` in C++ dient zur Deklaration von Variablen und Funktionen, die in anderen Dateien oder Modulen definiert sind. Es ermöglicht die Verwendung dieser externen Symbole in der aktuellen Datei.

## Dokumentation
In C++ wird `extern` verwendet, um die Sichtbarkeit von Variablen und Funktionen zu steuern. Das Schlüsselwort zeigt an, dass eine Variable oder Funktion, die in einer anderen Übersetzungseinheit (z.B. einer anderen Quelldatei) definiert ist, in der aktuellen Datei verwendet wird.

### Zweck
Der Hauptzweck von `extern` ist es, die Verknüpfung von Symbolen über verschiedene Dateien hinweg zu ermöglichen, ohne dass die Variablen oder Funktionen mehrmals definiert werden müssen.

### Verwendung
- **Variablen:** Wenn eine Variable mit `extern` deklariert wird, wird sie nicht neu definiert, sondern es wird auf eine bereits definierte Variable verwiesen.
- **Funktionen:** Funktionen sind standardmäßig extern, aber die Verwendung von `extern` kann die Absicht klarer machen.

### Details
- `extern` kann sowohl für globale Variablen als auch für Funktionen verwendet werden.
- Bei der Verwendung von `extern` für Variablen ist es wichtig, dass die Variable in einer anderen Datei tatsächlich definiert wird, sonst führt dies zu einem Linker-Fehler.
- Bei der Deklaration von Funktionen mit `extern` ist es üblich, die Rückgabetypen und Parameter anzugeben, um die Schnittstelle klar zu definieren.

## Beispiele
### Beispiel 1: Verwendung von `extern` mit Variablen
**Datei1.cpp**
```cpp
int globalVariable = 10; // Definition der globalen Variable
```

**Datei2.cpp**
```cpp
extern int globalVariable; // Deklaration der globalen Variable

void printGlobalVariable() {
    std::cout << globalVariable << std::endl; // Zugriff auf die externe Variable
}
```

### Beispiel 2: Verwendung von `extern` mit Funktionen
**Datei1.cpp**
```cpp
void printMessage(); // Funktionsprototyp

void printMessage() {
    std::cout << "Hallo, Welt!" << std::endl;
}
```

**Datei2.cpp**
```cpp
extern void printMessage(); // Deklaration der Funktion

int main() {
    printMessage(); // Aufruf der externen Funktion
    return 0;
}
```

## Erklärung
Ein häufiges Problem bei der Verwendung von `extern` ist das Vergessen der Definition der externen Variablen in einer anderen Datei, was zu Linker-Fehlern führt. Es ist wichtig, sicherzustellen, dass jede extern deklarierte Variable oder Funktion in einer Übersetzungseinheit vorhanden ist.

Ein weiterer häufiger Fehler ist die Verwirrung zwischen der Deklaration und der Definition. Eine Deklaration mit `extern` teilt dem Compiler lediglich mit, dass die Variable oder Funktion existiert, während die Definition den Speicher für die Variable reserviert oder die Funktion implementiert.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort `extern` in C++ ermöglicht die Deklaration von Variablen und Funktionen, die in anderen Dateien definiert sind, und fördert die Modularität und Wiederverwendbarkeit des Codes.