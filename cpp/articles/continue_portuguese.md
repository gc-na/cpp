<!--
Meta Description: # Comando `continue` em C++: Controle de Fluxo em Laços ## Sinopse O comando `continue` em C++ é utilizado para alterar o fluxo de execução em estrutu...
Meta Keywords: continue, loop, que, comando, para
-->

# Comando `continue` em C++: Controle de Fluxo em Laços

## Sinopse
O comando `continue` em C++ é utilizado para alterar o fluxo de execução em estruturas de repetição, como `for`, `while` e `do while`, permitindo que a iteração atual seja interrompida e a próxima iteração comece imediatamente.

## Documentação
O `continue` é uma instrução de controle de fluxo que, quando encontrada dentro de um loop, faz com que a execução salte para o início da próxima iteração. Isso é útil quando se deseja pular a execução de determinadas instruções dentro do loop sem sair dele completamente.

### Uso
O comando `continue` pode ser utilizado em loops das seguintes formas:

```cpp
for (inicialização; condição; incremento) {
    // Instruções
    if (condição_de_pulo) {
        continue; // Salta para a próxima iteração
    }
    // Mais instruções
}
```

```cpp
while (condição) {
    // Instruções
    if (condição_de_pulo) {
        continue; // Salta para a próxima iteração
    }
    // Mais instruções
}
```

### Detalhes
- O `continue` pode ser usado em loops aninhados, mas apenas afetará o loop mais interno onde está localizado.
- Ele não é aplicável fora de um contexto de loop; seu uso fora de um loop resultará em um erro de compilação.

## Exemplos
Aqui estão alguns exemplos práticos do uso do comando `continue` em C++:

### Exemplo 1: Usando `continue` em um loop `for`
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) {
            continue; // Pula números pares
        }
        cout << i << " "; // Imprime números ímpares
    }
    return 0;
}
```
*Saída: `1 3 5 7 9 `*

### Exemplo 2: Usando `continue` em um loop `while`
```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    while (i <= 10) {
        i++;
        if (i % 3 == 0) {
            continue; // Pula múltiplos de 3
        }
        cout << i << " "; // Imprime números que não são múltiplos de 3
    }
    return 0;
}
```
*Saída: `2 4 5 7 8 10 `*

## Explicação
Ao usar o comando `continue`, é importante ter cuidado para evitar criar loops infinitos. Por exemplo, se a condição de pulo nunca for falsa, o loop continuará a executar indefinidamente. Além disso, lembre-se de que `continue` só afeta o loop mais próximo, então seu uso em loops aninhados deve ser bem planejado.

### Armadilhas Comuns
- **Uso fora do loop**: Tentar usar `continue` fora de um loop resultará em um erro de compilação.
- **Condições de pulo mal definidas**: Assegure-se de que as condições que levam ao `continue` sejam cuidadosamente formuladas para evitar saídas inesperadas.

## Resumo em Uma Linha
O comando `continue` em C++ permite pular a iteração atual de um loop e iniciar a próxima, facilitando o controle de fluxo dentro de estruturas de repetição.