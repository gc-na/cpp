<!--
Meta Description: # thread_local in C++: Lokale Thread-Variablen ## Synopsis `thread_local` ist ein Spezifizierer in C++, der es ermöglicht, Variablen zu deklarieren, d...
Meta Keywords: thread, thread_local, der, variablen, die
-->

# thread_local in C++: Lokale Thread-Variablen 

## Synopsis
`thread_local` ist ein Spezifizierer in C++, der es ermöglicht, Variablen zu deklarieren, die für jeden Thread unabhängig sind. Dies bedeutet, dass jeder Thread seine eigene Instanz der Variablen hat.

## Dokumentation
Der `thread_local` Spezifizierer wurde in C++11 eingeführt und dient dazu, Daten zu isolieren, die spezifisch für den jeweiligen Thread sind. Variablen, die mit `thread_local` deklariert werden, existieren in einem eigenen Speicherbereich für jeden Thread, was zu einer besseren Performance und zu weniger Synchronisationsproblemen führen kann.

### Verwendung
Um eine Variable als `thread_local` zu deklarieren, wird der Spezifizierer vor dem Typ der Variablen platziert. Hier ist die allgemeine Syntax:

```cpp
thread_local Typ variableName;
```

### Details
- **Lebensdauer**: Eine `thread_local` Variable wird beim ersten Zugriff auf den jeweiligen Thread initialisiert und bleibt so lange existierend, bis der Thread endet.
- **Sichtbarkeit**: `thread_local` Variablen haben die Sichtbarkeit der Datei, wenn sie außerhalb von Funktionen deklariert werden, es sei denn, sie sind als `extern` deklariert.
- **Initialisierung**: Die Initialisierung von `thread_local` Variablen erfolgt in der Reihenfolge ihrer Deklaration innerhalb eines Threads.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `thread_local`:

### Einfaches Beispiel
```cpp
#include <iostream>
#include <thread>

thread_local int threadLocalVar = 0;

void increment() {
    ++threadLocalVar;
    std::cout << "Thread " << std::this_thread::get_id() << ": " << threadLocalVar << std::endl;
}

int main() {
    std::thread t1(increment);
    std::thread t2(increment);

    t1.join();
    t2.join();
    
    return 0;
}
```
In diesem Beispiel wird `threadLocalVar` für jeden Thread unabhängig erhöht.

### Komplexeres Beispiel
```cpp
#include <iostream>
#include <thread>

thread_local int threadLocalCounter = 0;

void threadFunction(int id) {
    for (int i = 0; i < 5; ++i) {
        threadLocalCounter++;
        std::cout << "Thread " << id << ": " << threadLocalCounter << std::endl;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
}

int main() {
    std::thread t1(threadFunction, 1);
    std::thread t2(threadFunction, 2);

    t1.join();
    t2.join();

    return 0;
}
```
Hier erhöht jeder Thread seinen eigenen Zähler und gibt ihn aus, ohne sich gegenseitig zu beeinflussen.

## Erklärung
### Häufige Fallstricke
- **Nicht initialisierte Variablen**: Wenn eine `thread_local` Variable nicht explizit initialisiert wird, wird sie mit dem Standardwert des Typs initialisiert. Dies kann zu unerwartetem Verhalten führen, wenn der Entwickler annimmt, dass die Variable einen spezifischen Wert hat.
- **Kombination mit statischen Variablen**: `thread_local` Variablen können nicht in einer Klasse oder Funktion deklariert werden, die statische Variablen enthält, da dies zu Problemen bei der Thread-Sicherheit führen kann.
- **Konstruktoren und Destruktoren**: Der Konstruktor einer `thread_local` Variable wird nur einmal pro Thread aufgerufen. Wenn der Thread endet, wird der Destruktor aufgerufen. Dies kann zu unerwartetem Verhalten führen, wenn nicht alle Ressourcen korrekt verwaltet werden.

## Ein-Satz-Zusammenfassung
`thread_local` ermöglicht die Definition von Variablen, die für jeden Thread unabhängig sind, und verbessert so die Thread-Sicherheit in C++.