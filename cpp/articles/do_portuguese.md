<!--
Meta Description: # O Comando "do" em C++: Estrutura de Controle de Fluxo ## Sinopse O comando `do` em C++ é utilizado para criar laços de repetição que garantem a exec...
Meta Keywords: condição, uma, para, bloco, código
-->

# O Comando "do" em C++: Estrutura de Controle de Fluxo

## Sinopse
O comando `do` em C++ é utilizado para criar laços de repetição que garantem a execução de um bloco de código pelo menos uma vez, antes de verificar a condição para continuar a execução do laço.

## Documentação
O comando `do` é parte da estrutura de controle de fluxo em C++. Ele permite a execução de um bloco de código repetidamente, desde que uma condição especificada permaneça verdadeira. A sintaxe básica é:

```cpp
do {
    // bloco de código a ser executado
} while (condição);
```

### Propósito
A principal finalidade do `do` é garantir que o bloco de código interno seja executado uma vez antes de avaliar a condição. Isso é particularmente útil em situações onde é necessário que o código execute pelo menos uma vez, como na coleta de entradas do usuário.

### Uso
O comando `do` é frequentemente utilizado em conjunto com a cláusula `while`. A condição é avaliada após a execução do bloco de código, permitindo que a execução continue ou pare com base no resultado dessa condição.

### Detalhes
- A condição deve ser do tipo booleano.
- Se a condição for falsa na primeira iteração, o bloco ainda será executado uma vez.
- O laço pode ser interrompido com a instrução `break`, e a execução pode ser saltada para a próxima iteração usando `continue`.

## Exemplos

**Exemplo 1: Contador Simples**
```cpp
#include <iostream>
using namespace std;

int main() {
    int contador = 0;
    do {
        cout << "Contador: " << contador << endl;
        contador++;
    } while (contador < 5);
    return 0;
}
```

**Exemplo 2: Entrada do Usuário**
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero;
    do {
        cout << "Digite um número positivo (ou negativo para sair): ";
        cin >> numero;
    } while (numero >= 0);
    return 0;
}
```

## Explicação
Um erro comum ao usar `do` é esquecer de que o bloco de código será executado pelo menos uma vez, não importando a condição. Além disso, é importante garantir que a condição eventualmente se torne falsa, caso contrário, o laço poderá resultar em um loop infinito.

Outro ponto a se considerar é a utilização de `break` e `continue`. O `break` pode ser utilizado para sair de um laço `do` prematuramente, enquanto o `continue` pode ser usado para pular a iteração atual e passar para a próxima.

## Resumo em Uma Linha
O comando `do` em C++ permite a execução de um bloco de código pelo menos uma vez antes de verificar uma condição para repetição.