<!--
Meta Description: # O que é "unsigned" em C++: Entendendo Tipos de Dados Inteiros ## Sinopse O termo "unsigned" em C++ refere-se a uma modificação dos tipos de dados in...
Meta Keywords: unsigned, tipos, que, valores, int
-->

# O que é "unsigned" em C++: Entendendo Tipos de Dados Inteiros

## Sinopse
O termo "unsigned" em C++ refere-se a uma modificação dos tipos de dados inteiros que permite representar apenas valores não negativos, aumentando assim o intervalo de valores que podem ser armazenados. É uma característica essencial para a manipulação eficiente de dados em programação.

## Documentação
Em C++, os tipos de dados inteiros podem ser declarados como "signed" ou "unsigned". Por padrão, os tipos inteiros como `int`, `short`, `long`, e `long long` são considerados "signed", o que significa que eles podem representar tanto números negativos quanto positivos. Por outro lado, ao declarar um tipo como "unsigned", você indica que ele só pode armazenar valores não negativos (0 e valores positivos).

### Propósito
O propósito do "unsigned" é fornecer uma gama maior de valores positivos para os tipos de dados inteiros, especialmente útil quando se sabe que os valores não podem ser negativos, como em contagens ou índices.

### Uso
Para declarar um tipo inteiro como "unsigned", basta adicionar a palavra-chave `unsigned` antes do tipo, por exemplo:

```cpp
unsigned int x;
unsigned short y;
unsigned long z;
```

### Detalhes
- **Intervalo**: O intervalo de um tipo "unsigned" é sempre maior que o de seu equivalente "signed". Por exemplo:
  - `unsigned int` pode armazenar valores de 0 a 4.294.967.295 (2^32 - 1) em um sistema de 32 bits, enquanto `int` (signed) varia de -2.147.483.648 a 2.147.483.647.
- **Conversão**: Cuidado ao realizar operações entre tipos "signed" e "unsigned", pois isso pode levar a comportamentos inesperados, como a promoção de um inteiro negativo a um número muito grande.
- **Operações**: Todas as operações aritméticas funcionam da mesma forma com tipos "unsigned", mas o resultado pode ser diferente se houver um estouro, levando a comportamentos não intencionais.

## Exemplos
Aqui estão alguns exemplos práticos do uso de "unsigned" em C++:

```cpp
#include <iostream>
using namespace std;

int main() {
    unsigned int a = 10;
    unsigned int b = 20;
    unsigned int resultado = a + b; // resultado será 30
    
    cout << "Resultado: " << resultado << endl; // Saída: Resultado: 30

    // Exemplo de estouro
    unsigned int c = 4294967295; // Valor máximo para unsigned int
    c = c + 1; // Causará um estouro, resultando em 0
    cout << "Após estouro: " << c << endl; // Saída: Após estouro: 0

    return 0;
}
```

## Explicação
Um dos erros mais comuns ao trabalhar com tipos "unsigned" é a tentativa de armazenar valores negativos, o que resultará em um erro de compilação ou comportamentos inesperados. Além disso, ao misturar tipos "signed" e "unsigned", é crucial ter cuidado, pois a promoção de um tipo "signed" negativo para um tipo "unsigned" pode resultar em um número muito grande, levando a resultados errôneos.

### Pontos a considerar:
- Sempre verifique se um valor pode ser negativo antes de usar "unsigned".
- Ao fazer operações entre diferentes tipos inteiros, considere o tipo maior para evitar estouros e resultados inesperados.
- Teste sempre os limites dos tipos "unsigned" para entender seu comportamento em casos de estouro.

## Resumo em Uma Linha
"Unsigned" em C++ é uma modificação de tipos inteiros que permite armazenar apenas valores não negativos, aumentando o intervalo de valores representáveis.