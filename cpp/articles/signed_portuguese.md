<!--
Meta Description: # O que é "signed" em C++: Tipos de Dados e Manipulação de Números Inteiros ## Sinopse O termo "signed" em C++ refere-se a um modificador de tipo que ...
Meta Keywords: signed, que, int, tipos, unsigned
-->

# O que é "signed" em C++: Tipos de Dados e Manipulação de Números Inteiros

## Sinopse
O termo "signed" em C++ refere-se a um modificador de tipo que permite que variáveis do tipo numérico armazenem valores positivos e negativos. A utilização deste modificador é crucial para a manipulação correta de números inteiros em aplicações que necessitam de operações com ambos os sinais.

## Documentação
Em C++, os tipos de dados numéricos podem ser classificados como "signed" (com sinal) ou "unsigned" (sem sinal). O modificador "signed" pode ser aplicado a tipos de dados inteiros como `int`, `short`, `long`, entre outros. Por padrão, os tipos inteiros em C++ são tratados como "signed", o que significa que eles podem representar valores negativos e positivos.

### Propósito
O principal objetivo do modificador "signed" é permitir que os desenvolvedores utilizem números negativos, o que é fundamental para muitas operações matemáticas e algoritmos que requerem manipulação de números inteiros.

### Uso
Para declarar uma variável como "signed", o modificador pode ser explicitamente incluído, embora não seja necessário, já que a maioria dos tipos inteiros são "signed" por padrão. A sintaxe é a seguinte:

```cpp
signed int numero = -10;
```

Entretanto, você pode também omitir o "signed" e usar apenas `int`, que é implicitamente assinado:

```cpp
int numero = -10;
```

### Detalhes
- O range de um tipo "signed" depende do número de bits que ele utiliza. Por exemplo, um `signed int` geralmente tem um intervalo de -2.147.483.648 a 2.147.483.647 em sistemas que utilizam 32 bits.
- É importante notar que a utilização de "signed" e "unsigned" pode afetar a lógica do seu programa, especialmente em operações aritméticas e comparações.

## Exemplos
Aqui estão alguns exemplos práticos do uso de "signed" em C++:

### Exemplo 1: Declaração simples
```cpp
#include <iostream>

int main() {
    signed int a = -5;
    signed int b = 10;
    signed int resultado = a + b;
    
    std::cout << "Resultado: " << resultado << std::endl; // Saída: Resultado: 5
    return 0;
}
```

### Exemplo 2: Comparação de valores
```cpp
#include <iostream>

int main() {
    signed int x = -3;
    signed int y = 2;

    if (x < y) {
        std::cout << "x é menor que y" << std::endl; // Saída: x é menor que y
    }
    return 0;
}
```

## Explicação
Um dos erros comuns ao trabalhar com tipos "signed" e "unsigned" é a comparação entre eles. Quando um número "signed" é comparado com um "unsigned", o "signed" pode ser promovido a "unsigned", levando a resultados inesperados. Por exemplo, um valor negativo será considerado muito grande quando convertido para um tipo "unsigned".

### Armadilhas Comuns
- **Comparações Misturadas**: Sempre evite comparações entre tipos "signed" e "unsigned" para evitar comportamentos inesperados.
- **Overflow**: O overflow em tipos "signed" pode resultar em comportamentos indefinidos, enquanto em "unsigned" resulta em um wrap-around.

## Resumo em Uma Linha
O modificador "signed" em C++ permite que variáveis inteiras representem tanto valores positivos quanto negativos, sendo essencial para operações que requerem manipulação de números com sinais.