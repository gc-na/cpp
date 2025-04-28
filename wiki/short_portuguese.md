<!--
Meta Description: # O Tipo de Dados "short" em C++ ## Sinopse O tipo de dado `short` em C++ é utilizado para armazenar números inteiros menores, oferecendo uma economia...
Meta Keywords: short, tipo, para, que, uma
-->

# O Tipo de Dados "short" em C++

## Sinopse
O tipo de dado `short` em C++ é utilizado para armazenar números inteiros menores, oferecendo uma economia de memória em comparação com o tipo `int`.

## Documentação
O `short` é um tipo de dado primitivo em C++ que representa um número inteiro de 16 bits. O intervalo de valores que pode ser armazenado varia de -32.768 a 32.767 para `short` assinado (signed) e de 0 a 65.535 para `short` não assinado (unsigned). O uso desse tipo é ideal em situações onde a economia de memória é crucial, como em sistemas embarcados ou em aplicações que manipulam grandes quantidades de dados inteiros.

### Uso
Para declarar uma variável do tipo `short`, você pode usar a seguinte sintaxe:

```cpp
short nome_variavel;
```

Você também pode inicializar a variável ao mesmo tempo:

```cpp
short idade = 25;
```

### Detalhes
- **Tamanho**: O tamanho do tipo `short` é garantido ser de pelo menos 16 bits, mas pode ser maior em algumas implementações.
- **Assinado vs Não Assinado**: Por padrão, `short` é assinado. Para declarar uma variável `short` não assinada, utilize a palavra-chave `unsigned`:

```cpp
unsigned short numeroNaoNegativo = 50000;
```

## Exemplos
Aqui estão alguns exemplos básicos de uso do tipo `short`:

```cpp
#include <iostream>
using namespace std;

int main() {
    short a = 10;
    short b = 20;
    short soma = a + b;

    cout << "A soma de " << a << " e " << b << " é: " << soma << endl;

    unsigned short c = 65000;
    cout << "O valor de c é: " << c << endl;

    return 0;
}
```

## Explicação
Um dos principais cuidados ao utilizar o tipo `short` é estar ciente do seu limite máximo e mínimo. Se você tentar armazenar um valor fora desse intervalo, ocorrerá um **overflow**, resultando em comportamento inesperado. Além disso, ao realizar operações aritméticas, é importante lembrar que os tipos menores podem ser promovidos a `int` durante as operações, o que pode levar a resultados diferentes do esperado se não for devidamente tratado.

## Resumo em Uma Linha
O tipo `short` em C++ é uma opção eficiente para armazenar inteiros menores, ocupando menos memória que o tipo `int`.