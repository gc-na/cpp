<!--
Meta Description: # noexcept em C++: Entenda a Garantia de Não Lançamento de Exceções ## Sinopse O `noexcept` é um especificador de função em C++ que indica que uma fun...
Meta Keywords: noexcept, uma, que, exceções, função
-->

# noexcept em C++: Entenda a Garantia de Não Lançamento de Exceções

## Sinopse
O `noexcept` é um especificador de função em C++ que indica que uma função não lançará exceções, permitindo otimizações de desempenho e melhor tratamento de erros.

## Documentação
O `noexcept` foi introduzido no C++11 e é utilizado para declarar que uma função não deve lançar exceções. Essa declaração é útil para o compilador, pois permite otimizações como a remoção de verificações de exceção durante a execução do código. O uso do `noexcept` pode levar a uma melhoria no desempenho, especialmente em contextos de exceção, como operações em containers da STL (Standard Template Library).

### Uso
A sintaxe básica do `noexcept` é a seguinte:

```cpp
void func() noexcept {
    // corpo da função
}
```

Além disso, é possível usar `noexcept` com uma expressão para indicar que a função não lançará exceções, dependendo do resultado de uma expressão booleana:

```cpp
void func() noexcept(expression) {
    // corpo da função
}
```

### Detalhes
- **Exceções**: Se uma função marcada como `noexcept` lançar uma exceção, o programa chamará `std::terminate()`, encerrando a execução abruptamente.
- **Compilação**: O `noexcept` pode ser útil para funções que realizam operações que não devem falhar, como alocações de memória seguras ou manipulações de dados em tempo crítico.
- **Desempenho**: Funções `noexcept` podem ser otimizadas de maneira mais agressiva pelo compilador, resultando em um código mais eficiente.

## Exemplos

### Exemplo 1: Função Básica com noexcept

```cpp
#include <iostream>

void func() noexcept {
    std::cout << "Esta função não lança exceções." << std::endl;
}

int main() {
    func();
    return 0;
}
```

### Exemplo 2: Uso de noexcept com Expressão

```cpp
#include <iostream>

bool willNotThrow() {
    return true; // Esta função não lança exceções
}

void func() noexcept(willNotThrow()) {
    std::cout << "Esta função também é garantida para não lançar exceções." << std::endl;
}

int main() {
    func();
    return 0;
}
```

## Explicação
### Erros Comuns
- **Lançamento de Exceções**: O erro mais comum ao usar `noexcept` é esquecer que, se uma exceção for lançada, o programa se encerrará. Isso deve ser considerado ao usar `noexcept` em funções que chamam outras funções que podem lançar exceções.
- **Apropriação de Recursos**: Em funções `noexcept`, cuidado deve ser tomado ao alocar recursos. Se uma alocação de memória falhar e lançar uma exceção, isso não será tratado, resultando no encerramento do programa.

### Notas Adicionais
- O `noexcept` é especialmente útil em funções de movimentação e cópia, onde a alocação de novos recursos é uma operação crítica.
- É uma prática comum usar `noexcept` em funções que manipulam tipos que garantem não lançar exceções, como ponteiros brutos ou tipos que usam a alocação de memória sem exceção.

## Resumo em Uma Linha
O `noexcept` é um especificador em C++ que garante que uma função não lançará exceções, permitindo otimizações de desempenho e uma melhor gestão de erros.