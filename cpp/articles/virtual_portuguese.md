<!--
Meta Description: # Virtual em C++: Entendendo o Polimorfismo e Herança ## Sinopse O modificador "virtual" em C++ é uma característica fundamental que permite a impleme...
Meta Keywords: virtual, base, std, animal, classe
-->

# Virtual em C++: Entendendo o Polimorfismo e Herança

## Sinopse
O modificador "virtual" em C++ é uma característica fundamental que permite a implementação do polimorfismo, permitindo que métodos em classes derivadas sejam chamados através de referências ou ponteiros de classes base.

## Documentação
O modificador `virtual` é utilizado em métodos de uma classe base para indicar que eles podem ser sobrescritos nas classes derivadas. Quando um método é declarado como virtual, o C++ utiliza a *tabela virtual* (vtable) para resolver chamadas a esses métodos em tempo de execução, permitindo que a implementação correta seja utilizada, dependendo do tipo do objeto referenciado.

### Propósito
O propósito do `virtual` é permitir que a chamada de métodos seja decidida em tempo de execução, facilitando a extensão e a manutenção de código por meio de herança e polimorfismo.

### Uso
Para declarar um método como virtual, usa-se a palavra-chave `virtual` na classe base. A sobrescrita do método na classe derivada é feita normalmente, sem a necessidade de usar a palavra-chave `virtual` novamente (embora seja uma boa prática fazê-lo).

```cpp
class Base {
public:
    virtual void mostrar() {
        std::cout << "Classe Base" << std::endl;
    }
};

class Derivada : public Base {
public:
    void mostrar() override {  // 'override' é opcional mas recomendado
        std::cout << "Classe Derivada" << std::endl;
    }
};
```

## Exemplos

### Exemplo Básico de Uso

```cpp
#include <iostream>

class Animal {
public:
    virtual void fazerSom() {
        std::cout << "Som de animal" << std::endl;
    }
};

class Cachorro : public Animal {
public:
    void fazerSom() override {
        std::cout << "Au Au!" << std::endl;
    }
};

void emitirSom(Animal* animal) {
    animal->fazerSom();  // Chamada polimórfica
}

int main() {
    Animal* a = new Animal();
    Animal* c = new Cachorro();

    emitirSom(a);  // Saída: Som de animal
    emitirSom(c);  // Saída: Au Au!

    delete a;
    delete c;
    return 0;
}
```

### Exemplo com Ponteiro de Classe Base

```cpp
class Forma {
public:
    virtual double area() = 0;  // Método virtual puro
};

class Retangulo : public Forma {
private:
    double largura, altura;
public:
    Retangulo(double l, double a) : largura(l), altura(a) {}

    double area() override {
        return largura * altura;
    }
};

int main() {
    Forma* forma = new Retangulo(5.0, 4.0);
    std::cout << "Área do Retângulo: " << forma->area() << std::endl;  // Saída: Área do Retângulo: 20
    delete forma;
    return 0;
}
```

## Explicação
Um erro comum ao trabalhar com métodos virtuais é esquecer de usar o operador `delete` em ponteiros de classes derivadas, resultando em vazamentos de memória. Além disso, a falta de um destrutor virtual na classe base pode causar comportamentos indesejados, pois o destrutor da classe derivada não será chamado, resultando em vazamentos de recursos.

Outro ponto importante é a diferença entre métodos virtuais e métodos virtuais puros. Um método virtual puro é um método que não possui implementação na classe base e deve ser implementado obrigatoriamente nas classes derivadas, caracterizando um tipo abstrato.

## Resumo em Uma Linha
O modificador `virtual` em C++ permite a implementação do polimorfismo, possibilitando que métodos em classes derivadas sejam chamados corretamente através de referências ou ponteiros de classes base.