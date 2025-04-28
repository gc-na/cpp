<!--
Meta Description: # Classe em C++: Entenda como Funciona a Programação Orientada a Objetos ## Sinopse Uma classe em C++ é um modelo que define a estrutura e o comportam...
Meta Keywords: que, public, classe, uma, class
-->

# Classe em C++: Entenda como Funciona a Programação Orientada a Objetos

## Sinopse
Uma classe em C++ é um modelo que define a estrutura e o comportamento de objetos. Ela permite encapsular dados e funções que operam nesses dados, formando a base da programação orientada a objetos.

## Documentação
Em C++, uma classe é uma construção que combina dados e funções que manipulam esses dados. A definição de uma classe é feita utilizando a palavra-chave `class`, seguida do nome da classe e um bloco de definições. A classe pode conter atributos (variáveis) e métodos (funções) que definem o comportamento do objeto.

### Estrutura Básica de uma Classe
```cpp
class NomeDaClasse {
public:
    // Atributos
    int atributo1;
    float atributo2;

    // Métodos
    void metodo1() {
        // Implementação do método
    }
};
```

### Atributos e Métodos
- **Atributos**: Variáveis que armazenam o estado do objeto.
- **Métodos**: Funções que definem o comportamento do objeto. Podem ser públicas, privadas ou protegidas, controlando o acesso a eles.

### Construtores e Destrutores
Classes em C++ podem ter construtores, que são métodos especiais chamados quando um objeto é criado, e destrutores, que são chamados quando o objeto é destruído.

```cpp
class Exemplo {
public:
    Exemplo() { // Construtor
        // Inicialização
    }

    ~Exemplo() { // Destrutor
        // Limpeza
    }
};
```

### Herança
C++ permite que uma classe herde atributos e métodos de outra. Isso promove a reutilização de código e a criação de hierarquias.

```cpp
class ClasseBase {
public:
    void metodoBase() {}
};

class ClasseDerivada : public ClasseBase {
public:
    void metodoDerivado() {}
};
```

## Exemplos
### Exemplo Básico de Classe
```cpp
#include <iostream>
using namespace std;

class Carro {
public:
    string modelo;
    int ano;

    void mostrarInfo() {
        cout << "Modelo: " << modelo << ", Ano: " << ano << endl;
    }
};

int main() {
    Carro meuCarro;
    meuCarro.modelo = "Fusca";
    meuCarro.ano = 1975;
    meuCarro.mostrarInfo();
    return 0;
}
```

### Exemplo de Herança
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void fazerSom() {
        cout << "Animal faz som!" << endl;
    }
};

class Cachorro : public Animal {
public:
    void fazerSom() {
        cout << "Cachorro late!" << endl;
    }
};

int main() {
    Cachorro meuCachorro;
    meuCachorro.fazerSom();
    return 0;
}
```

## Explicação
Uma armadilha comum ao usar classes em C++ é não entender o conceito de escopo e visibilidade. É crucial definir corretamente se um atributo ou método deve ser `public`, `private` ou `protected`. Além disso, esquecendo de definir um construtor padrão pode gerar erros ao tentar instanciar um objeto.

Outro ponto importante é a gestão de memória, especialmente ao usar ponteiros dentro de classes. O uso inadequado pode levar a vazamentos de memória. Sempre que alocar memória dinamicamente, lembre-se de liberar a memória no destrutor.

## Resumo em Uma Linha
Classes em C++ são estruturas fundamentais da programação orientada a objetos, permitindo a encapsulação, herança e manipulação de dados de forma eficiente.