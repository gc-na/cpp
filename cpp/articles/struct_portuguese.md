<!--
Meta Description: # Estruturas em C++: Compreendendo o Uso do "struct" ## Sinopse Neste artigo, exploraremos o conceito de "struct" em C++, uma ferramenta fundamental p...
Meta Keywords: struct, uma, structs, para, que
-->

# Estruturas em C++: Compreendendo o Uso do "struct"

## Sinopse
Neste artigo, exploraremos o conceito de "struct" em C++, uma ferramenta fundamental para a definição de tipos de dados personalizados, permitindo organizar e manipular informações de maneira eficiente.

## Documentação
No C++, uma `struct` (estrutura) é um tipo de dado que permite agrupar variáveis de diferentes tipos sob um mesmo nome. As `structs` são frequentemente utilizadas para representar entidades que possuem múltiplos atributos. A principal diferença entre `structs` e classes em C++ é o nível de acesso padrão: as variáveis de uma `struct` são públicas por padrão, enquanto em uma classe, são privadas.

### Propósito
As `structs` são usadas para criar tipos de dados complexos, facilitando a gestão de dados relacionados entre si, como os atributos de um objeto no mundo real.

### Uso
A sintaxe básica para definir uma `struct` é a seguinte:

```cpp
struct NomeDaStruct {
    Tipo atributo1;
    Tipo atributo2;
    // ...
};
```

Para declarar e utilizar uma `struct`, você pode fazer o seguinte:

```cpp
struct Pessoa {
    std::string nome;
    int idade;
};

Pessoa pessoa1;
pessoa1.nome = "João";
pessoa1.idade = 30;
```

## Exemplos
Veja alguns exemplos básicos de uso de `struct` em C++:

### Exemplo 1: Definindo uma Estrutura Simples

```cpp
#include <iostream>
#include <string>

struct Carro {
    std::string marca;
    int ano;
};

int main() {
    Carro meuCarro;
    meuCarro.marca = "Toyota";
    meuCarro.ano = 2020;

    std::cout << "Marca: " << meuCarro.marca << ", Ano: " << meuCarro.ano << std::endl;
    return 0;
}
```

### Exemplo 2: Estruturas com Funções

```cpp
#include <iostream>

struct Retangulo {
    float largura;
    float altura;

    float area() {
        return largura * altura;
    }
};

int main() {
    Retangulo ret;
    ret.largura = 5.0;
    ret.altura = 3.0;

    std::cout << "Área do retângulo: " << ret.area() << std::endl;
    return 0;
}
```

## Explicação
Embora as `structs` sejam semelhantes às classes, é importante notar algumas diferenças. Por exemplo, as `structs` não suportam herança múltipla de forma tão direta quanto as classes. Além disso, ao usar `structs`, é comum esquecer de inicializar os atributos, o que pode levar a comportamentos inesperados. Portanto, sempre que possível, inicialize os membros da `struct` no momento da definição.

Outro ponto importante é que, ao usar `structs`, se você não definir um construtor, o compilador fornecerá um construtor padrão que não inicializa os membros. Isso pode causar problemas se você tentar acessar membros não inicializados.

## Resumo em Uma Linha
As `structs` em C++ são utilizadas para agrupar variáveis de diferentes tipos, facilitando a criação de tipos de dados personalizados e a organização de informações relacionadas.