<!--
Meta Description: # Operadores em C++: Tudo o que Você Precisa Saber ## Sinopse Os operadores em C++ são símbolos que realizam operações em variáveis e valores. Este ar...
Meta Keywords: operadores, cout, endl, valor, lógico
-->

# Operadores em C++: Tudo o que Você Precisa Saber

## Sinopse
Os operadores em C++ são símbolos que realizam operações em variáveis e valores. Este artigo aborda os diferentes tipos de operadores disponíveis na linguagem, sua sintaxe, uso e exemplos práticos.

## Documentação
Os operadores em C++ são fundamentais para realizar diversas operações, como aritméticas, lógicas e relacionais. Eles permitem manipular dados, realizar cálculos e controlar o fluxo da aplicação. Abaixo estão os principais tipos de operadores em C++:

### 1. Operadores Aritméticos
- **Adição (`+`)**: Soma dois operandos.
- **Subtração (`-`)**: Subtrai o segundo operando do primeiro.
- **Multiplicação (`*`)**: Multiplica dois operandos.
- **Divisão (`/`)**: Divide o primeiro operando pelo segundo.
- **Módulo (`%`)**: Retorna o resto da divisão entre dois operandos.

### 2. Operadores Relacionais
- **Igual a (`==`)**: Verifica se dois valores são iguais.
- **Diferente de (`!=`)**: Verifica se dois valores são diferentes.
- **Maior que (`>`)**: Verifica se o primeiro valor é maior que o segundo.
- **Menor que (`<`)**: Verifica se o primeiro valor é menor que o segundo.
- **Maior ou igual a (`>=`)**: Verifica se o primeiro valor é maior ou igual ao segundo.
- **Menor ou igual a (`<=`)**: Verifica se o primeiro valor é menor ou igual ao segundo.

### 3. Operadores Lógicos
- **E lógico (`&&`)**: Retorna verdadeiro se ambos os operandos são verdadeiros.
- **Ou lógico (`||`)**: Retorna verdadeiro se pelo menos um dos operandos é verdadeiro.
- **Não lógico (`!`)**: Inverte o valor lógico do operando.

### 4. Operadores de Atribuição
- **Atribuição simples (`=`)**: Atribui o valor da direita à variável da esquerda.
- **Atribuição aditiva (`+=`)**: Adiciona o valor da direita à variável da esquerda e armazena o resultado na esquerda.
- **Atribuição subtrativa (`-=`)**, **multiplicativa (`*=`)**, **divisiva (`/=`)** e **módulo (`%=`)** seguem a mesma lógica.

### 5. Outros Operadores
- **Operadores Unários**: Como incremento (`++`) e decremento (`--`) que aumentam ou diminuem o valor de uma variável em um.
- **Operador Ternário (`? :`)**: Uma forma concisa de expressar uma condição, retornando um valor baseado na veracidade de uma expressão booleana.

## Exemplos
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 20;

    // Operadores Aritméticos
    cout << "Soma: " << (a + b) << endl; // Adição
    cout << "Subtração: " << (b - a) << endl; // Subtração
    cout << "Multiplicação: " << (a * b) << endl; // Multiplicação
    cout << "Divisão: " << (b / a) << endl; // Divisão
    cout << "Módulo: " << (b % a) << endl; // Módulo

    // Operadores Relacionais
    cout << "Igual: " << (a == b) << endl; // Igual a
    cout << "Diferente: " << (a != b) << endl; // Diferente de

    // Operadores Lógicos
    bool x = true, y = false;
    cout << "E lógico: " << (x && y) << endl; // E lógico
    cout << "Ou lógico: " << (x || y) << endl; // Ou lógico

    // Operador Ternário
    int max = (a > b) ? a : b;
    cout << "Máximo: " << max << endl; // Operador ternário

    return 0;
}
```

## Explicação
Um erro comum ao utilizar operadores é a confusão entre operadores de atribuição e operadores de comparação. Por exemplo, usar `=` em vez de `==` pode levar a resultados inesperados, pois `=` é um operador de atribuição e `==` é um operador de comparação. Além disso, operadores lógicos como `&&` e `||` devem ser utilizados com precisão em expressões condicionais para evitar resultados errôneos.

## Resumo em Uma Linha
Os operadores em C++ são símbolos utilizados para realizar operações em variáveis e valores, abrangendo aritmética, comparação, lógica e atribuição.