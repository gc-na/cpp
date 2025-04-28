<!--
Meta Description: # Comando "case" em C++: Entenda o Controle de Fluxo ## Sinopse O comando `case` em C++ é parte da declaração `switch`, que permite ao programador exe...
Meta Keywords: case, break, switch, código, cout
-->

# Comando "case" em C++: Entenda o Controle de Fluxo

## Sinopse
O comando `case` em C++ é parte da declaração `switch`, que permite ao programador executar diferentes seções de código com base no valor de uma variável. É uma ferramenta poderosa para simplificar o controle de fluxo em programas.

## Documentação
O comando `case` é utilizado dentro da estrutura de controle `switch`, que avalia uma expressão e compara seu valor com constantes definidas. Cada constante é precedida por uma palavra-chave `case`, permitindo que diferentes blocos de código sejam executados conforme o valor correspondente.

### Sintaxe
```cpp
switch (expressão) {
    case constante1:
        // Código a ser executado se expressão == constante1
        break;
    case constante2:
        // Código a ser executado se expressão == constante2
        break;
    // ...
    default:
        // Código a ser executado se nenhum case for correspondido
}
```

### Propósito
O propósito principal do comando `case` é facilitar a seleção entre múltiplas opções, tornando o código mais legível e organizado em comparação com múltiplas instruções `if-else`.

### Uso
- O `switch` avalia a expressão uma única vez.
- Cada `case` deve ser seguido por um bloco de código e um `break` para evitar a execução de casos subsequentes.
- O `default` serve como um caso "pega-tudo" e é opcional.

## Exemplos
### Exemplo Básico
```cpp
#include <iostream>
using namespace std;

int main() {
    int dia = 3;

    switch (dia) {
        case 1:
            cout << "Domingo" << endl;
            break;
        case 2:
            cout << "Segunda-feira" << endl;
            break;
        case 3:
            cout << "Terça-feira" << endl;
            break;
        default:
            cout << "Dia inválido" << endl;
    }

    return 0;
}
```

### Exemplo Sem `break`
```cpp
#include <iostream>
using namespace std;

int main() {
    int numero = 2;

    switch (numero) {
        case 1:
            cout << "Um" << endl;
        case 2:
            cout << "Dois" << endl;
        case 3:
            cout << "Três" << endl;
            break;
        default:
            cout << "Número inválido" << endl;
    }

    return 0;
}
```
*Saída:*
```
Dois
Três
```

## Explicação
### Armadilhas Comuns
- **Falta de `break`:** Se esquecer de adicionar a instrução `break` após um `case`, o programa continuará a executar os blocos de código dos casos subsequentes até encontrar um `break`, o que pode não ser o comportamento desejado.
- **Tipos de Dados:** O valor da expressão no `switch` deve ser um tipo inteiro ou enum. Outros tipos, como strings, não são permitidos diretamente em um `switch`.
- **Constantes Repetidas:** Cada `case` deve ter um valor único. Se duas constantes iguais forem definidas, o compilador gerará um erro.

## Resumo em Uma Linha
O comando `case` em C++ é utilizado dentro da estrutura `switch` para facilitar o controle de fluxo, permitindo a execução de diferentes blocos de código com base no valor de uma variável.