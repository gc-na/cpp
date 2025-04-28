<!--
Meta Description: # Template em C++: Entendendo e Aplicando ## Sinopse Os templates em C++ são uma poderosa característica que permite a criação de funções e classes ge...
Meta Keywords: template, que, templates, uma, não
-->

# Template em C++: Entendendo e Aplicando

## Sinopse
Os templates em C++ são uma poderosa característica que permite a criação de funções e classes genéricas, possibilitando a reutilização de código e a implementação de algoritmos que operam em diferentes tipos de dados.

## Documentação
### O que são Templates?
Templates são uma forma de programação genérica em C++. Eles permitem que você defina uma função ou uma classe com um tipo de dado genérico, que é especificado posteriormente na instância do template. Isso ajuda a criar código mais flexível e reutilizável.

### Por que usar Templates?
- **Reutilização de Código**: Permitem que você escreva uma única versão de um algoritmo que pode trabalhar com diferentes tipos de dados.
- **Tipo Seguro**: O compilador verifica os tipos em tempo de compilação, reduzindo erros em tempo de execução.
- **Desempenho**: Como os templates são resolvidos em tempo de compilação, não há sobrecarga em tempo de execução.

### Sintaxe
A sintaxe básica para declarar um template é a seguinte:

```cpp
template <typename T>
T funcao(T parametro) {
    // implementação
}
```

Para classes, a sintaxe é semelhante:

```cpp
template <typename T>
class Classe {
public:
    T atributo;
    void metodo(T parametro) {
        // implementação
    }
};
```

## Exemplos
### Exemplo de Função Template
```cpp
#include <iostream>
using namespace std;

template <typename T>
T soma(T a, T b) {
    return a + b;
}

int main() {
    cout << soma(5, 10) << endl; // Saída: 15
    cout << soma(5.5, 6.5) << endl; // Saída: 12.0
    return 0;
}
```

### Exemplo de Classe Template
```cpp
#include <iostream>
using namespace std;

template <typename T>
class Caixa {
private:
    T conteudo;
public:
    void guardar(T item) {
        conteudo = item;
    }
    T abrir() {
        return conteudo;
    }
};

int main() {
    Caixa<int> caixaInt;
    caixaInt.guardar(42);
    cout << caixaInt.abrir() << endl; // Saída: 42

    Caixa<string> caixaString;
    caixaString.guardar("Olá, Mundo!");
    cout << caixaString.abrir() << endl; // Saída: Olá, Mundo!
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Erros de Compilação**: Erros de tipo podem ser difíceis de entender, especialmente se você não especificar corretamente o tipo do template.
- **Instanciação Excessiva**: Cada instância de um template gera uma nova versão da função ou classe, o que pode aumentar o tamanho do código compilado se não for controlado.
- **Falta de Especialização**: Se o template não for suficientemente especializado, você pode acabar com um comportamento inesperado.

### Notas Adicionais
- A especialização de templates é uma técnica que permite definir um comportamento diferente para um tipo específico.
- Templates não podem ser usados com tipos incompletos, como classes que ainda não foram definidas.

## Resumo em Uma Linha
Templates em C++ permitem a criação de funções e classes genéricas, aumentando a reutilização e flexibilidade do código.