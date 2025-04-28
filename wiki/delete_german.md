<!--
Meta Description: # C++ `delete`: Speicherfreigabe für dynamische Objekte ## Synopsis Das Schlüsselwort `delete` in C++ wird verwendet, um den Speicher, der für dynamis...
Meta Keywords: delete, die, für, speicher, auf
-->

# C++ `delete`: Speicherfreigabe für dynamische Objekte

## Synopsis
Das Schlüsselwort `delete` in C++ wird verwendet, um den Speicher, der für dynamisch allokierte Objekte reserviert wurde, freizugeben. Es spielt eine entscheidende Rolle beim Verhindern von Speicherlecks und der effizienten Verwaltung von Ressourcen.

## Dokumentation
### Zweck
`delete` wird in C++ verwendet, um den Speicher, der für Objekte, die mit `new` erstellt wurden, wieder freizugeben. Dies ist besonders wichtig in Programmen, die dynamische Speicherzuweisungen verwenden, um sicherzustellen, dass Ressourcen nach ihrem Gebrauch ordnungsgemäß verwaltet werden.

### Verwendung
Die Syntax für `delete` ist:
```cpp
delete pointer;
```
Hierbei ist `pointer` ein Zeiger auf das Objekt, dessen Speicher freigegeben werden soll. 

### Details
- `delete` sollte nur auf Zeiger angewendet werden, die mit `new` erstellt wurden. Die Verwendung von `delete` auf einem Zeiger, der nicht mit `new` erstellt wurde, führt zu undefiniertem Verhalten.
- Es gibt auch `delete[]`, das verwendet wird, um den Speicher für Arrays freizugeben, die mit `new[]` erstellt wurden:
```cpp
delete[] pointer;
```
- Nach der Verwendung von `delete` wird empfohlen, den Zeiger auf `nullptr` zu setzen, um sicherzustellen, dass keine weiteren Zugriffe auf den freigegebenen Speicher erfolgen.

## Beispiele
### Einfaches Beispiel
```cpp
#include <iostream>

int main() {
    int* p = new int(5);  // Dynamisch ein int allokieren
    std::cout << *p << std::endl;  // Ausgabe: 5
    delete p;  // Speicher freigeben
    p = nullptr;  // Zeiger auf nullptr setzen
    return 0;
}
```

### Beispiel für ein Array
```cpp
#include <iostream>

int main() {
    int* arr = new int[5];  // Dynamisch ein Array allokieren
    for (int i = 0; i < 5; ++i) {
        arr[i] = i;  // Array initialisieren
    }
    delete[] arr;  // Speicher für das Array freigeben
    arr = nullptr;  // Zeiger auf nullptr setzen
    return 0;
}
```

## Erklärung
Ein häufiger Fehler ist die Verwendung von `delete` auf einem Zeiger, der bereits freigegeben wurde. Dies kann zu schwerwiegenden Fehlern führen, wie z.B. einem doppelten Löschen (double delete). Es ist auch wichtig, die Unterscheidung zwischen `delete` und `delete[]` zu beachten, da die falsche Verwendung zu Speicherlecks oder undefiniertem Verhalten führen kann. Achten Sie darauf, dass Sie `delete[]` nur für Arrays verwenden, die mit `new[]` erstellt wurden.

## Ein-Satz-Zusammenfassung
Das `delete`-Schlüsselwort in C++ wird verwendet, um den Speicher dynamisch allokierter Objekte freizugeben und ist entscheidend für die effiziente Verwaltung von Ressourcen.