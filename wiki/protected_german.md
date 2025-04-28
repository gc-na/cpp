<!--
Meta Description: # Das Schlüsselwort "protected" in C++ ## Synopsis Das Schlüsselwort "protected" in C++ ist ein Zugriffsmodifikator, der es ermöglicht, dass Mitgliede...
Meta Keywords: protected, der, von, die, klassen
-->

# Das Schlüsselwort "protected" in C++

## Synopsis
Das Schlüsselwort "protected" in C++ ist ein Zugriffsmodifikator, der es ermöglicht, dass Mitglieder einer Klasse nur innerhalb dieser Klasse und in abgeleiteten Klassen zugänglich sind. Es spielt eine entscheidende Rolle in der objektorientierten Programmierung, insbesondere beim Erstellen von Vererbungshierarchien.

## Dokumentation
Der Zugriffsmodifikator "protected" wird verwendet, um den Zugriff auf Klassenmitglieder (Attribute und Methoden) zu steuern. Mitglieder, die als "protected" deklariert sind, können von der Klasse selbst sowie von ihren abgeleiteten Klassen (Unterklassen) genutzt werden, jedoch nicht von Instanzen anderer Klassen.

### Zweck
Der Hauptzweck von "protected" ist es, eine kontrollierte Schnittstelle für abgeleitete Klassen bereitzustellen, während gleichzeitig der Zugriff von externen Klassen eingeschränkt wird. Dies fördert die Kapselung und ermöglicht es, dass Unterklassen die Funktionalität ihrer Basisklasse erweitern, ohne dass die Implementierungsdetails von außen sichtbar sind.

### Verwendung
Um ein Mitglied einer Klasse als "protected" zu deklarieren, verwenden Sie das Schlüsselwort "protected" vor der Deklaration des Mitglieds:

```cpp
class Basisklasse {
protected:
    int geschuetztesAttribut;

    void geschuetzteMethode() {
        // Implementierung
    }
};
```

In einer abgeleiteten Klasse können Sie auf die geschützten Mitglieder der Basisklasse zugreifen:

```cpp
class AbgeleiteteKlasse : public Basisklasse {
public:
    void zugriffAufGeschuetztes() {
        geschuetztesAttribut = 10; // Zugriff auf geschütztes Attribut
        geschuetzteMethode();      // Aufruf geschützter Methode
    }
};
```

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von "protected":

### Beispiel 1: Zugriff auf geschützte Mitglieder
```cpp
class Fahrzeug {
protected:
    int geschwindigkeit;

public:
    Fahrzeug() : geschwindigkeit(0) {}
};

class Auto : public Fahrzeug {
public:
    void beschleunigen(int wert) {
        geschwindigkeit += wert; // Zugriff auf geschütztes Attribut
    }
};
```

### Beispiel 2: Vererbung und geschützte Methoden
```cpp
class Tier {
protected:
    void lautGeben() {
        std::cout << "Tier macht Geräusch" << std::endl;
    }
};

class Hund : public Tier {
public:
    void bellen() {
        lautGeben(); // Aufruf der geschützten Methode
    }
};
```

## Erklärung
Ein häufiger Fehler beim Arbeiten mit dem "protected"-Zugriffsmodifikator ist, dass Entwickler versuchen, auf geschützte Mitglieder von außerhalb der Klassenhierarchie zuzugreifen, was zu Kompilierungsfehlern führt. Beachten Sie, dass "protected" nur innerhalb der Klasse selbst und in abgeleiteten Klassen zugänglich ist. Ein weiterer Punkt ist, dass "protected" nicht den Zugriff von Instanzen der Klasse oder von externen Funktionen erlaubt, was oft missverstanden wird.

Zusätzlich sollten Entwickler vorsichtig sein, wenn sie "protected" verwenden, da dies die Kapselung beeinträchtigen kann, wenn abgeleitete Klassen nicht ordnungsgemäß gestaltet sind. Es ist wichtig, die Hierarchie und die Beziehungen zwischen Klassen klar zu definieren, um die Vorteile von "protected" optimal zu nutzen.

## Ein Satz Zusammenfassung
Das "protected"-Schlüsselwort in C++ ermöglicht den kontrollierten Zugriff auf Klassenmitglieder in der Basisklasse und den abgeleiteten Klassen, fördert jedoch die Kapselung und die Strukturierung des Codes.