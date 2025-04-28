<!--
Meta Description: # Estrutura Condicional "if" em C++ ## Sinopse A estrutura condicional "if" em C++ permite que o programa execute um bloco de código apenas se uma con...
Meta Keywords: código, que, else, bloco, uma
-->

# Estrutura Condicional "if" em C++

## Sinopse
A estrutura condicional "if" em C++ permite que o programa execute um bloco de código apenas se uma condição específica for verdadeira. É uma ferramenta fundamental para o controle do fluxo de execução em programas.

## Documentação
A estrutura "if" é usada para tomar decisões no código. Sua sintaxe básica é:

```cpp
if (condição) {
    // bloco de código a ser executado se a condição for verdadeira
}
```

### Propósito
O propósito da estrutura "if" é avaliar uma expressão booleana (uma condição) e, dependendo do resultado (verdadeiro ou falso), decidir se um determinado bloco de código deve ser executado.

### Uso
A estrutura "if" pode ser utilizada sozinha ou em conjunto com outras estruturas condicionais, como "else" e "else if". A sintaxe completa é:

```cpp
if (condição) {
    // bloco de código se a condição for verdadeira
} else if (outra_condição) {
    // bloco de código se a outra condição for verdadeira
} else {
    // bloco de código se nenhuma das condições anteriores for verdadeira
}
```

### Detalhes
- **Condições**: As condições podem ser expressões booleanas que resultam em verdadeiro (`true`) ou falso (`false`).
- **Aninhamento**: É possível aninhar várias estruturas "if" para verificar múltiplas condições.
- **Escopo**: O escopo das variáveis definidas dentro do bloco "if" só existe dentro desse bloco.

## Exemplos
### Exemplo Básico

```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 10;

    if (numero > 5) {
        cout << "O número é maior que 5." << endl;
    }

    return 0;
}
```

### Exemplo com Else

```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 3;

    if (numero > 5) {
        cout << "O número é maior que 5." << endl;
    } else {
        cout << "O número não é maior que 5." << endl;
    }

    return 0;
}
```

### Exemplo com Else If

```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 5;

    if (numero > 5) {
        cout << "O número é maior que 5." << endl;
    } else if (numero == 5) {
        cout << "O número é igual a 5." << endl;
    } else {
        cout << "O número é menor que 5." << endl;
    }

    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Comparação de Tipos**: Certifique-se de que a condição esteja comparando tipos compatíveis. Comparar um inteiro com um caractere, por exemplo, pode levar a comportamentos inesperados.
- **Uso de Operadores Lógicos**: Ao usar operadores lógicos (`&&`, `||`), é importante entender a precedência e o agrupamento das expressões para evitar erros lógicos.
- **Blocos de Código**: É uma boa prática usar chaves `{}` mesmo para blocos que contêm apenas uma linha de código. Isso melhora a legibilidade e evita erros ao adicionar novas instruções.

## Resumo em Uma Linha
A estrutura condicional "if" em C++ é uma ferramenta essencial para executar blocos de código com base na avaliação de condições booleanas.