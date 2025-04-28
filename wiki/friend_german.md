<!--
Meta Description: # Freundschaft in C++: Die Verwendung von "friend" ## Synopsis In C++ ermöglicht das Schlüsselwort "friend" einer Funktion oder einer Klasse den Zugri...
Meta Keywords: klasse, friend, die, einer, klassea
-->

# Freundschaft in C++: Die Verwendung von "friend"

## Synopsis
In C++ ermöglicht das Schlüsselwort "friend" einer Funktion oder einer Klasse den Zugriff auf private und geschützte Mitglieder einer anderen Klasse. Dies ist besonders nützlich, um den Zugriff auf Daten zu steuern und gleichzeitig die Kapselung zu wahren.

## Documentation
Das Schlüsselwort "friend" wird in C++ verwendet, um die Zugriffsrechte zwischen Klassen und Funktionen zu erweitern. Standardmäßig sind Mitglieder einer Klasse nur innerhalb ihrer eigenen Instanz zugänglich. Durch die Deklaration einer Funktion oder einer Klasse als "friend" innerhalb einer Klasse kann diese auf alle Mitglieder (einschließlich privater und geschützter) der Klasse zugreifen.

### Zweck
Der Hauptzweck von "friend" besteht darin, den Zugriff auf private Daten zu ermöglichen, ohne die Datenkapselung vollständig aufzugeben. Dies ist besonders hilfreich in Situationen, in denen zwei Klassen eng zusammenarbeiten und es notwendig ist, dass eine Klasse auf die internen Daten einer anderen Klasse zugreifen kann.

### Verwendung
Um eine Funktion oder eine andere Klasse als Freund zu deklarieren, fügen Sie das Schlüsselwort "friend" in die Definition der Klasse ein:

```cpp
class KlasseA;

class KlasseB {
public:
    void methode(KlasseA &a);
};

class KlasseA {
    friend class KlasseB; // KlasseB hat Zugriff auf die privaten Mitglieder von KlasseA
private:
    int geheimnis = 42;
};
```

In diesem Beispiel hat `KlasseB` Zugriff auf das private Mitglied `geheimnis` von `KlasseA`.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von "friend":

### Beispiel 1: Freundliche Funktion
```cpp
#include <iostream>

class Klasse;

void freundlicheFunktion(Klasse &objekt);

class Klasse {
private:
    int wert = 10;
    
public:
    friend void freundlicheFunktion(Klasse &objekt);
};

void freundlicheFunktion(Klasse &objekt) {
    std::cout << "Der Wert ist: " << objekt.wert << std::endl;
}

int main() {
    Klasse obj;
    freundlicheFunktion(obj);
    return 0;
}
```

### Beispiel 2: Freundliche Klasse
```cpp
#include <iostream>

class KlasseA;

class KlasseB {
public:
    void zeigeWert(KlasseA &a);
};

class KlasseA {
private:
    int wert = 20;

    friend class KlasseB; // KlasseB ist ein Freund
};

void KlasseB::zeigeWert(KlasseA &a) {
    std::cout << "Der Wert von KlasseA ist: " << a.wert << std::endl;
}

int main() {
    KlasseA a;
    KlasseB b;
    b.zeigeWert(a);
    return 0;
}
```

## Explanation
Ein häufiger Fehler bei der Verwendung von "friend" ist, dass Programmierer den Zugriff auf private Mitglieder übersehen, wenn sie nicht die richtige Freundschaftsdeklaration hinzufügen. Zudem kann das übermäßige Verwenden von "friend" zu einem Verlust der Kapselung führen, was die Wartbarkeit des Codes beeinträchtigen kann. 

Ein weiterer wichtiger Punkt ist, dass "friend"-Deklarationen nicht vererbt werden. Wenn eine Klasse als Freund einer anderen Klasse deklariert ist, bedeutet das nicht, dass ihre Unterklassen automatisch auch Freunde sind.

## One Line Summary
Das Schlüsselwort "friend" in C++ ermöglicht einer Funktion oder Klasse den Zugriff auf private und geschützte Mitglieder einer anderen Klasse, ohne die Kapselung zu verletzen.