<!--
Meta Description: # Operador "ou" (or) em C++ ## Sinopse O operador "ou" (or) em C++ é um operador lógico que realiza a operação de disjunção entre dois operandos, reto...
Meta Keywords: operador, que, expressões, expressão, uma
-->

# Operador "ou" (or) em C++

## Sinopse
O operador "ou" (or) em C++ é um operador lógico que realiza a operação de disjunção entre dois operandos, retornando verdadeiro se pelo menos um dos operandos for verdadeiro. É amplamente utilizado em expressões condicionais e na tomada de decisões em programas.

## Documentação
O operador "ou" é representado pelo símbolo `||` em C++. Ele avalia duas expressões booleanas e retorna um valor verdadeiro (`true`) se pelo menos uma das expressões for verdadeira (`true`). Caso ambas as expressões sejam falsas (`false`), o resultado será falso.

### Propósito
O operador "ou" é essencial para a lógica de controle em C++, permitindo que programadores verifiquem múltiplas condições em uma única expressão condicional.

### Uso
O operador "ou" pode ser utilizado em instruções `if`, `while` e em qualquer lugar onde uma expressão booleana é esperada. A operação é avaliada da seguinte forma:
- Se a primeira expressão for verdadeira, a segunda expressão não é avaliada (curto-circuito).
- Se a primeira expressão for falsa, a segunda expressão é avaliada.

### Detalhes
- Sintaxe: `expressao1 || expressao2`
- Tipos de operandos: As expressões podem ser de qualquer tipo que possa ser convertido em um valor booleano (incluindo expressões que retornam `bool`).
- O operador retorna um valor booleano (`true` ou `false`).

## Exemplos

### Exemplo 1: Uso Básico
```cpp
#include <iostream>
using namespace std;

int main() {
    bool a = true;
    bool b = false;

    if (a || b) {
        cout << "Pelo menos uma das condições é verdadeira." << endl;
    } else {
        cout << "Ambas as condições são falsas." << endl;
    }

    return 0;
}
```

### Exemplo 2: Avaliação Curto-Circuito
```cpp
#include <iostream>
using namespace std;

bool funcao() {
    cout << "Função chamada!" << endl;
    return true;
}

int main() {
    bool resultado = false || funcao();
    cout << "Resultado: " << resultado << endl;

    return 0;
}
```
Neste exemplo, a função `funcao()` não é chamada porque a primeira expressão (`false`) é avaliada como falsa.

## Explicação
Um erro comum ao usar o operador "ou" é assumir que ambas as expressões sempre serão avaliadas. Devido ao comportamento de curto-circuito, se a primeira expressão já for verdadeira, a segunda não será avaliada, o que pode levar a resultados inesperados, especialmente se a segunda expressão contém chamadas de função ou acessos a recursos que não devem ser executados se a primeira for verdadeira.

Além disso, é importante lembrar que o operador "ou" é diferente do operador bitwise "ou" (`|`), que opera em bits individuais. Usar o operador bitwise em vez do operador lógico pode causar comportamentos inesperados em expressões booleanas.

## Resumo em Uma Linha
O operador "ou" (or) em C++ permite a combinação de expressões booleanas, retornando verdadeiro se pelo menos uma delas for verdadeira.