<!--
Meta Description: # O Modificador de Acesso "protected" em C++ ## Sinopse O modificador de acesso "protected" em C++ é utilizado para controlar o acesso a membros de um...
Meta Keywords: protected, classes, acesso, base, valorprotegido
-->

# O Modificador de Acesso "protected" em C++

## Sinopse
O modificador de acesso "protected" em C++ é utilizado para controlar o acesso a membros de uma classe, permitindo que eles sejam acessados por classes derivadas e amigos, mas não por instâncias de outras classes.

## Documentação
O modificador "protected" é um dos três níveis de acesso em C++, os outros sendo "public" e "private". Quando um membro (variável ou método) de uma classe é declarado como "protected", ele pode ser acessado diretamente por:

- Classes derivadas (subclasses).
- Classes amigas (friend classes).

### Propósito
O principal objetivo do modificador "protected" é permitir que subclasses acessem e modifiquem os membros da classe base de forma segura, promovendo o encapsulamento enquanto ainda permite uma certa flexibilidade para herança.

### Uso
Para declarar um membro como "protected", você deve usar a palavra-chave `protected` antes da declaração do membro dentro da classe:

```cpp
class Base {
protected:
    int valorProtegido;
};
```

Em uma classe derivada, o membro "protected" pode ser acessado diretamente:

```cpp
class Derivada : public Base {
public:
    void modificarValor(int novoValor) {
        valorProtegido = novoValor;  // Acesso permitido
    }
};
```

## Exemplos

### Exemplo 1: Uso básico do "protected"
```cpp
#include <iostream>
using namespace std;

class Base {
protected:
    int valorProtegido;

public:
    Base() : valorProtegido(0) {}
};

class Derivada : public Base {
public:
    void setValor(int valor) {
        valorProtegido = valor;  // Acesso ao membro protegido
    }

    void mostrarValor() {
        cout << "Valor: " << valorProtegido << endl;
    }
};

int main() {
    Derivada d;
    d.setValor(10);
    d.mostrarValor();  // Saída: Valor: 10
    return 0;
}
```

### Exemplo 2: Acesso a "protected" em classes amigas
```cpp
#include <iostream>
using namespace std;

class Base {
protected:
    int valorProtegido;

public:
    Base() : valorProtegido(0) {}
    friend class Amiga; // Declaração de classe amiga
};

class Amiga {
public:
    void alterarValor(Base &b, int novoValor) {
        b.valorProtegido = novoValor;  // Acesso permitido
    }
};

int main() {
    Base b;
    Amiga a;
    a.alterarValor(b, 20);
    // Não é possível mostrar o valor protegido diretamente
    return 0;
}
```

## Explicação
Embora "protected" ofereça um meio de acesso para classes derivadas, é importante lembrar que membros "protected" não podem ser acessados diretamente por instâncias de outras classes que não sejam subclasses ou classes amigas. Isso pode levar a confusões, especialmente para desenvolvedores iniciantes. Além disso, o uso excessivo de membros "protected" pode levar a um design de código menos robusto, onde subclasses dependem muito da implementação da classe base.

### Armadilhas Comuns
1. **Acesso Indevido:** Tentar acessar membros "protected" de uma instância de uma classe que não é derivada resultará em um erro de compilação.
2. **Dificuldade em Manter o Código:** Um uso excessivo de membros "protected" pode criar um acoplamento forte entre classes e dificultar a manutenção do código.
3. **Confusão com "private":** Membros "private" não são acessíveis, nem mesmo para classes derivadas, o que pode ser confuso para novos desenvolvedores.

## Resumo em Uma Linha
O modificador "protected" em C++ permite o acesso a membros de classes por classes derivadas e amigas, promovendo a herança controlada.