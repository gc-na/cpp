<!--
Meta Description: # Das Schlüsselwort "this" in C++ ## Synopsis Das Schlüsselwort "this" in C++ ist ein Zeiger, der auf das aktuelle Objekt verweist, in dessen Kontext ...
Meta Keywords: wert, ist, der, auf, beispiel
-->

# Das Schlüsselwort "this" in C++

## Synopsis
Das Schlüsselwort "this" in C++ ist ein Zeiger, der auf das aktuelle Objekt verweist, in dessen Kontext eine Methode oder ein Konstruktor aufgerufen wird. Es wird häufig verwendet, um auf Mitglieder des Objekts zuzugreifen oder um Konflikte zwischen lokalen Variablen und Mitgliedsvariablen zu vermeiden.

## Dokumentation
In C++ ist "this" ein konstanter Zeiger (vom Typ `ClassName*`), der innerhalb der Mitgliederfunktionen einer Klasse automatisch verfügbar ist. Es ermöglicht den Zugriff auf die Instanzvariablen und Methoden des aktuellen Objekts. Die Verwendung von "this" wird besonders nützlich, wenn Parameter oder lokale Variablen denselben Namen wie die Mitgliedsvariablen haben. 

### Zweck
- **Zugriff auf Mitglieder**: "this" ermöglicht den Zugriff auf die Mitglieder der Klasse.
- **Unterscheidung von Namen**: Es hilft, Namenskonflikte zwischen den Parametern und Mitgliedervariablen zu vermeiden.
- **Rückgabewert**: "this" kann verwendet werden, um den aktuellen Objektzeiger zurückzugeben, was in Methoden wie Operatorüberladungen nützlich ist.

### Verwendung
Das Schlüsselwort "this" kann in allen nicht-statischen Mitgliedsfunktionen verwendet werden. In statischen Funktionen ist "this" nicht verfügbar, da diese Funktionen nicht an eine spezifische Instanz der Klasse gebunden sind.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von "this":

### Beispiel 1: Zugriff auf Mitglieder
```cpp
class Beispiel {
public:
    int wert;

    Beispiel(int wert) {
        this->wert = wert;  // Verwendung von "this" zum Unterscheiden der Variablen
    }

    void zeigeWert() {
        std::cout << "Wert: " << this->wert << std::endl;  // Zugriff über "this"
    }
};

int main() {
    Beispiel b(42);
    b.zeigeWert();  // Ausgabe: Wert: 42
    return 0;
}
```

### Beispiel 2: Rückgabe von "this"
```cpp
class Beispiel {
public:
    Beispiel* setzeWert(int wert) {
        this->wert = wert;
        return this;  // Rückgabe des aktuellen Objekts
    }

    void zeigeWert() {
        std::cout << "Wert: " << this->wert << std::endl;
    }

private:
    int wert;
};

int main() {
    Beispiel b;
    b.setzeWert(10)->zeigeWert();  // Kettenaufruf
    return 0;
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von "this" ist die Annahme, dass es in statischen Mitgliedsfunktionen verfügbar ist. Da statische Funktionen nicht an eine Instanz gebunden sind, ist "this" dort nicht definiert. 

Ein weiterer Punkt ist, dass "this" nicht verändert werden kann. Es ist ein konstanter Zeiger, sodass Sie ihm nicht einen anderen Objektzeiger zuweisen können. Dies schützt vor unbeabsichtigten Änderungen des Zeigers während der Laufzeit.

## Einzeilensummary
Das Schlüsselwort "this" in C++ verweist auf das aktuelle Objekt und ermöglicht den Zugriff auf seine Mitglieder und Methoden.