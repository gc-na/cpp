<!--
Meta Description: # O Que é "const" em C++: Entenda a Constância em Programação ## Sinopse O modificador "const" em C++ é utilizado para declarar que uma variável, obje...
Meta Keywords: const, int, que, uma, não
-->

# O Que é "const" em C++: Entenda a Constância em Programação

## Sinopse
O modificador "const" em C++ é utilizado para declarar que uma variável, objeto ou membro de classe não pode ser alterado após sua inicialização. Essa característica promove a segurança e a integridade dos dados no código.

## Documentação
### Propósito
O "const" é uma palavra-chave que permite ao programador garantir que determinados valores não sejam modificados durante a execução do programa. Isso é especialmente útil em contextos onde a proteção contra modificações acidentais é crucial para a lógica da aplicação.

### Uso
O "const" pode ser aplicado em variáveis, ponteiros e métodos de classe. Aqui estão algumas maneiras comuns de utilizá-lo:

1. **Constantes**: Declara uma variável que não pode ser alterada.
   ```cpp
   const int MAX_VALUE = 100;
   ```
   
2. **Ponteiros**: Um ponteiro para um tipo constante, ou um ponteiro constante.
   ```cpp
   const int* p1; // Ponteiro para um inteiro constante
   int* const p2; // Ponteiro constante para um inteiro
   ```

3. **Métodos Constantes**: Em classes, métodos marcados como "const" não podem modificar os membros da classe.
   ```cpp
   class Exemplo {
   public:
       void metodoConstante() const {
           // Não pode modificar membros da classe
       }
   };
   ```

### Detalhes
- **Escopo**: O modificador "const" deve ser aplicado no momento da declaração. Uma vez que uma variável é declarada como "const", qualquer tentativa de modificar seu valor resultará em um erro de compilação.
- **Tipo de Dados**: "const" pode ser aplicado a qualquer tipo de dado, incluindo primitivos, classes e estruturas.

## Exemplos
### Exemplo 1: Variável Constante
```cpp
#include <iostream>
using namespace std;

int main() {
    const int numero = 10;
    // numero = 20; // Erro: tentativa de modificar uma variável constante
    cout << "O número é: " << numero << endl;
    return 0;
}
```

### Exemplo 2: Ponteiro Constante
```cpp
#include <iostream>
using namespace std;

int main() {
    int valor = 5;
    const int* p = &valor;
    // *p = 10; // Erro: não pode modificar o valor através de um ponteiro constante
    cout << "Valor: " << *p << endl;
    return 0;
}
```

### Exemplo 3: Método Constante
```cpp
#include <iostream>
using namespace std;

class Contador {
private:
    int count;
public:
    Contador() : count(0) {}
    
    void incrementar() {
        count++;
    }
    
    void mostrar() const {
        cout << "Contador: " << count << endl; // Pode acessar count porque não é uma modificação
    }
};

int main() {
    Contador c;
    c.incrementar();
    c.mostrar();
    return 0;
}
```

## Explicação
### Armadilhas Comuns
1. **Modificações Indesejadas**: Um erro comum é tentar modificar uma variável ou membro de classe declarado como "const", o que levará a erros de compilação.
2. **Confusão de Ponteiros**: Ao trabalhar com ponteiros constantes, é fácil confundir a constância do ponteiro com a constância do valor apontado. É importante entender a diferença entre `const int*` e `int* const`.

### Notas Adicionais
- O uso de "const" não só melhora a segurança do código, mas também pode ajudar o compilador a otimizar o desempenho.
- É uma boa prática usar "const" sempre que possível, especialmente em funções que não precisam modificar seus parâmetros.

## Resumo em Uma Linha
O "const" em C++ é um modificador que garante que variáveis e membros não sejam alterados após a inicialização, promovendo segurança e integridade de dados.