<!--
Meta Description: # nullptr em C++: O Novo Padrão para Ponteiros Nulos ## Sinopse O `nullptr` é uma palavra-chave introduzida no C++11 que representa um ponteiro nulo d...
Meta Keywords: nullptr, ponteiro, nulo, que, para
-->

# nullptr em C++: O Novo Padrão para Ponteiros Nulos

## Sinopse
O `nullptr` é uma palavra-chave introduzida no C++11 que representa um ponteiro nulo de forma segura e tipada, substituindo o uso de `NULL` e `0` como representações de ponteiros nulos.

## Documentação
O `nullptr` é um literal que representa um valor nulo para ponteiros, proporcionando uma maneira mais clara e segura de indicá-los. Diferentemente de `NULL`, que é frequentemente definido como `0` ou `((void*)0)`, o `nullptr` é do tipo `std::nullptr_t`, que pode ser convertido para qualquer tipo de ponteiro, mas não para um inteiro ou qualquer outro tipo não relacionado a ponteiros.

### Propósito
O principal objetivo do `nullptr` é eliminar ambiguidade na sobrecarga de funções e garantir que os ponteiros nulos sejam sempre interpretados corretamente, independentemente do contexto.

### Uso
`nullptr` pode ser usado em qualquer lugar onde um ponteiro nulo é necessário, como inicialização de ponteiros, comparação e passagem como argumento em funções.

#### Exemplos de Uso
```cpp
#include <iostream>

void func(int* ptr) {
    if (ptr == nullptr) {
        std::cout << "O ponteiro é nulo." << std::endl;
    } else {
        std::cout << "O ponteiro não é nulo." << std::endl;
    }
}

int main() {
    int* p1 = nullptr; // Inicializando um ponteiro nulo
    int a = 10;
    int* p2 = &a; // Ponteiro para uma variável

    func(p1); // Saída: O ponteiro é nulo.
    func(p2); // Saída: O ponteiro não é nulo.

    return 0;
}
```

## Explicação
Embora `nullptr` seja uma melhoria sobre `NULL`, ainda é importante entender algumas armadilhas comuns:

1. **Ambiguidade em Sobrecargas**: Antes do C++11, usar `NULL` poderia causar confusão em funções sobrecarregadas. Com `nullptr`, essa ambiguidade é resolvida, já que o compilador pode distinguir entre um ponteiro nulo e um inteiro.

2. **Conversões de Tipo**: `nullptr` não pode ser convertido para um tipo inteiro, o que ajuda a evitar erros acidentais que podem ocorrer quando se usa `NULL` ou `0`.

3. **Compatibilidade**: `nullptr` é totalmente compatível com qualquer tipo de ponteiro, permitindo um código mais limpo e fácil de manter.

## Resumo em Uma Linha
O `nullptr` é uma representação segura e tipada de um ponteiro nulo em C++, eliminando ambiguidades associadas ao uso de `NULL` e `0`.