<!--
Meta Description: # Der Zugriffsmodifikator "public" in C++ ## Synopsis Der Zugriffsmodifikator `public` in C++ ermöglicht den Zugriff auf Klassenmitglieder von überall...
Meta Keywords: der, public, die, von, ist
-->

# Der Zugriffsmodifikator "public" in C++

## Synopsis
Der Zugriffsmodifikator `public` in C++ ermöglicht den Zugriff auf Klassenmitglieder von überall im Programm. Er ist ein zentraler Bestandteil der objektorientierten Programmierung und spielt eine entscheidende Rolle bei der Implementierung von Schnittstellen und der Datenkapselung.

## Dokumentation
In C++ definiert der Zugriffsmodifikator `public`, welche Mitglieder (Attribute und Methoden) einer Klasse von außerhalb der Klasse zugänglich sind. Standardmäßig sind Mitglieder einer Klasse `private`, was bedeutet, dass sie nur innerhalb der Klasse selbst zugänglich sind. Durch die Verwendung von `public` können Programmierer jedoch spezifische Funktionen und Daten für andere Teile des Programms verfügbar machen.

### Verwendung
Um ein Mitglied einer Klasse als `public` zu deklarieren, wird der Modifikator einfach vor der Mitgliedserklärung platziert. Hier ist ein einfaches Beispiel:

```cpp
class Beispiel {
public:
    int zahl;

    void setZahl(int n) {
        zahl = n;
    }
};
```

In diesem Beispiel ist `zahl` ein öffentliches Attribut und die Methode `setZahl` ist ebenfalls öffentlich, was bedeutet, dass sie von außerhalb der Klasse aufgerufen werden kann.

### Details
- **Zugriffsmodifikatoren:** In C++ gibt es drei Hauptzugriffsmodifikatoren: `public`, `private` und `protected`. 
- **Sichtbarkeit:** Mitglieder, die als `public` deklariert sind, können von jedem Code, der Zugriff auf die Instanz der Klasse hat, verwendet werden. Das fördert die Interoperabilität zwischen den Klassen.
- **Datenkapselung:** Obwohl `public` den Zugriff auf Mitglieder ermöglicht, sollte es mit Bedacht verwendet werden, um die Integrität der Daten zu gewährleisten.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `public` in C++:

### Beispiel 1: Öffentliches Attribut
```cpp
#include <iostream>

class Auto {
public:
    std::string marke;

    void setMarke(std::string m) {
        marke = m;
    }
};

int main() {
    Auto meinAuto;
    meinAuto.setMarke("BMW");
    std::cout << "Marke: " << meinAuto.marke << std::endl;
    return 0;
}
```

### Beispiel 2: Öffentliches Mitglied mit Konstruktor
```cpp
#include <iostream>

class Person {
public:
    std::string name;

    Person(std::string n) {
        name = n;
    }
};

int main() {
    Person person("Max");
    std::cout << "Name: " << person.name << std::endl;
    return 0;
}
```

## Erklärung
Ein häufiger Fehler ist die Überbeanspruchung des `public` Modifikators. Es ist wichtig, eine Balance zwischen Zugänglichkeit und Datenkapselung zu finden. Wenn zu viele Mitglieder als `public` deklariert werden, kann dies zu einem Verlust der Kontrolle über die Integrität der Daten führen. 

Ein weiterer Punkt ist, dass öffentliche Methoden dazu verwendet werden sollten, die Interaktion mit den privaten Mitgliedern zu steuern, um sicherzustellen, dass die Klasse in einem konsistenten Zustand bleibt.

## Ein-Satz-Zusammenfassung
Der Zugriffsmodifikator `public` in C++ ermöglicht den uneingeschränkten Zugriff auf Klassenmitglieder von außen und ist entscheidend für die Interaktion zwischen Klassen.