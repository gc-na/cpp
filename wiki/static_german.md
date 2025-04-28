<!--
Meta Description: # C++ Schlüsselwort "static": Eine umfassende Anleitung ## Synopsis Das Schlüsselwort `static` in C++ wird verwendet, um die Sichtbarkeit und Lebensda...
Meta Keywords: static, statische, die, zähler, und
-->

# C++ Schlüsselwort "static": Eine umfassende Anleitung

## Synopsis
Das Schlüsselwort `static` in C++ wird verwendet, um die Sichtbarkeit und Lebensdauer von Variablen und Funktionen zu steuern. Es ermöglicht die Konservierung des Wertes einer Variablen über mehrere Funktionsaufrufe hinweg und definiert den Gültigkeitsbereich von Variablen und Funktionen im Dateikontext.

## Dokumentation
In C++ hat das Schlüsselwort `static` mehrere Anwendungsmöglichkeiten:

1. **Statische lokale Variablen**: Wenn eine Variable innerhalb einer Funktion als `static` deklariert wird, behält sie ihren Wert zwischen den Funktionsaufrufen. Diese Variablen werden nur einmal initialisiert und existieren, bis das Programm endet.

2. **Statische Klassenmitglieder**: Klassen können statische Mitglieder haben, die von allen Instanzen der Klasse geteilt werden. Statische Mitglieder haben eine einzige Kopie, die für alle Objekte der Klasse zugänglich ist.

3. **Statische Funktionen**: Eine Funktion, die als `static` deklariert ist, hat einen Gültigkeitsbereich, der auf die Datei beschränkt ist, in der sie definiert wurde. Das bedeutet, dass sie nicht von anderen Dateien aus aufgerufen werden kann.

### Verwendung
Das Schlüsselwort `static` wird in verschiedenen Kontexten eingesetzt:

- **Statische lokale Variablen**:
  ```cpp
  void funktion() {
      static int zähler = 0; // Initialisierung nur einmal
      zähler++;
      std::cout << zähler << std::endl;
  }
  ```

- **Statische Klassenmitglieder**:
  ```cpp
  class Beispiel {
  public:
      static int zähler;
      Beispiel() { zähler++; }
  };
  int Beispiel::zähler = 0; // Definition des statischen Mitglieds
  ```

- **Statische Funktionen**:
  ```cpp
  static void hilfsfunktion() {
      std::cout << "Dies ist eine statische Funktion." << std::endl;
  }
  ```

## Beispiele
Hier sind einige einfache Beispiele zur Veranschaulichung der Verwendung von `static`:

1. **Statische lokale Variable**:
   ```cpp
   #include <iostream>

   void zähle() {
       static int zähler = 0; // Wird nur einmal initialisiert
       zähler++;
       std::cout << "Zähler: " << zähler << std::endl;
   }

   int main() {
       zähle(); // Ausgabe: Zähler: 1
       zähle(); // Ausgabe: Zähler: 2
       return 0;
   }
   ```

2. **Statische Klassenmitglieder**:
   ```cpp
   #include <iostream>

   class Auto {
   public:
       static int anzahl;
       Auto() { anzahl++; }
   };

   int Auto::anzahl = 0; // Definition des statischen Mitglieds

   int main() {
       Auto a1;
       Auto a2;
       std::cout << "Anzahl der Autos: " << Auto::anzahl << std::endl; // Ausgabe: Anzahl der Autos: 2
       return 0;
   }
   ```

3. **Statische Funktion**:
   ```cpp
   #include <iostream>

   static void geheimeFunktion() {
       std::cout << "Diese Funktion ist nur in dieser Datei sichtbar." << std::endl;
   }

   int main() {
       geheimeFunktion(); // Aufruf der statischen Funktion
       return 0;
   }
   ```

## Erklärung
Ein häufiges Missverständnis ist die Verwendung von statischen Variablen in multithreaded Umgebungen. Statische Variablen sind nicht threadsicher, und bei paralleler Ausführung können unerwartete Ergebnisse auftreten. Es ist wichtig zu beachten, dass statische Mitglieder einer Klasse nicht an eine bestimmte Instanz gebunden sind und daher von allen Instanzen der Klasse geteilt werden.

Ein weiterer Punkt ist, dass die Sichtbarkeit von statischen Funktionen auf die Datei beschränkt ist, in der sie definiert sind. Dies kann nützlich sein, um Namenskonflikte zu vermeiden, führt aber manchmal zu Verwirrung, wenn man versucht, die Funktion außerhalb ihrer Datei zu verwenden.

## Ein-Satz-Zusammenfassung
Das `static` Schlüsselwort in C++ dient dazu, die Sichtbarkeit und Lebensdauer von Variablen und Funktionen zu steuern, was die Programmierung und den Umgang mit Speicher erheblich beeinflusst.