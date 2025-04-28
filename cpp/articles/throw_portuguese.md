<!--
Meta Description: # O Comando "throw" em C++: Tratamento de Exceções ## Sinopse O comando `throw` em C++ é utilizado para iniciar a manipulação de exceções, permitindo ...
Meta Keywords: throw, que, exceção, para, std
-->

# O Comando "throw" em C++: Tratamento de Exceções

## Sinopse
O comando `throw` em C++ é utilizado para iniciar a manipulação de exceções, permitindo que um programa trate erros e situações excepcionais de uma forma controlada e previsível.

## Documentação
O `throw` é uma palavra-chave em C++ que permite lançar exceções. Quando um erro ocorre em um programa, o `throw` pode ser utilizado para sinalizar que uma condição excepcional foi encontrada. O controle do fluxo do programa é transferido para um bloco de tratamento de exceções, permitindo que o erro seja tratado de forma adequada.

### Propósito
O principal propósito do `throw` é facilitar o tratamento de erros, separando a lógica normal do programa da lógica de tratamento de erros.

### Uso
Para utilizar o `throw`, basta especificar a expressão ou objeto que representa a exceção a ser lançada. Essa exceção pode ser de qualquer tipo, mas é comum usar tipos derivados da classe `std::exception` para garantir uma manipulação adequada.

### Sintaxe
```cpp
throw expressão;
```

## Exemplos

### Exemplo 1: Lançando uma Exceção Simples
```cpp
#include <iostream>
#include <stdexcept>

void funcaoQueLanca() {
    throw std::runtime_error("Ocorreu um erro!");
}

int main() {
    try {
        funcaoQueLanca();
    } catch (const std::runtime_error& e) {
        std::cout << "Exceção capturada: " << e.what() << std::endl;
    }
    return 0;
}
```

### Exemplo 2: Lançando Exceções Personalizadas
```cpp
#include <iostream>
#include <exception>

class MinhaExcecao : public std::exception {
public:
    const char* what() const noexcept override {
        return "Minha exceção personalizada foi lançada!";
    }
};

void funcaoComExcecaoPersonalizada() {
    throw MinhaExcecao();
}

int main() {
    try {
        funcaoComExcecaoPersonalizada();
    } catch (const MinhaExcecao& e) {
        std::cout << "Exceção capturada: " << e.what() << std::endl;
    }
    return 0;
}
```

## Explicação
Um dos principais pontos a se considerar ao utilizar `throw` é que a exceção lançada deve ser tratada em um bloco `try` correspondente. Caso contrário, o programa terminará abruptamente com um erro. Além disso, é importante lançar exceções de tipos apropriados e utilizar as práticas recomendadas para garantir que a memória e os recursos sejam gerenciados corretamente.

Outro ponto a se notar é que, ao lançar uma exceção, o controle do fluxo é transferido imediatamente para o bloco `catch` mais próximo que pode tratar a exceção. Isso pode levar a um desempenho comprometido se não for usado com cautela, especialmente em loops críticos de desempenho.

## Resumo em Uma Linha
O comando `throw` em C++ é utilizado para lançar exceções, permitindo o tratamento de erros de forma controlada e organizada.