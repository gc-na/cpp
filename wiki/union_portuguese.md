<!--
Meta Description: # União em C++: Entenda o Uso e Funcionalidade ## Sinopse A união (`union`) em C++ é uma estrutura de dados que permite armazenar diferentes tipos de ...
Meta Keywords: union, inteiro, valor, decimal, dado
-->

# União em C++: Entenda o Uso e Funcionalidade

## Sinopse
A união (`union`) em C++ é uma estrutura de dados que permite armazenar diferentes tipos de dados na mesma área de memória, economizando espaço e possibilitando o uso eficiente de recursos.

## Documentação
A `union` é um tipo de dado que permite que várias variáveis compartilhem o mesmo espaço de memória. Ao contrário das `structs`, onde cada membro possui sua própria memória, em uma `union`, todos os membros ocupam a mesma localização na memória, o que significa que, em um dado momento, apenas um membro pode conter um valor válido.

### Propósito
A `union` é especialmente útil em situações onde você precisa armazenar diferentes tipos de dados, mas não simultaneamente. Por exemplo, ela pode ser usada em sistemas embarcados onde a economia de memória é crucial.

### Uso
A sintaxe para declarar uma `union` é similar à de uma `struct`:

```cpp
union NomeDaUniao {
    Tipo1 membro1;
    Tipo2 membro2;
    // Outros membros...
};
```

Para acessar os membros da `union`, você deve usar o operador de acesso (.) como em uma `struct`.

### Exemplo de Declaração
```cpp
#include <iostream>
using namespace std;

union Dados {
    int inteiro;
    float decimal;
    char caractere;
};

int main() {
    Dados dado;
    dado.inteiro = 42;
    cout << "Inteiro: " << dado.inteiro << endl;

    dado.decimal = 3.14f; // Sobrescreve o valor do inteiro
    cout << "Decimal: " << dado.decimal << endl;

    dado.caractere = 'A'; // Sobrescreve o valor do decimal
    cout << "Caractere: " << dado.caractere << endl;

    return 0;
}
```

## Exemplos
### Exemplo 1: Uso Básico
```cpp
#include <iostream>
using namespace std;

union Valor {
    int inteiro;
    float decimal;
};

int main() {
    Valor v;
    v.inteiro = 10;
    cout << "Inteiro: " << v.inteiro << endl;

    v.decimal = 20.5;
    cout << "Decimal: " << v.decimal << endl; // O valor do inteiro é sobrescrito

    return 0;
}
```

### Exemplo 2: Composição em Struct
```cpp
#include <iostream>
using namespace std;

struct Exemplo {
    union {
        int inteiro;
        float decimal;
    } valor;
    bool tipo; // true para inteiro, false para decimal
};

int main() {
    Exemplo e;
    e.tipo = true;
    if (e.tipo) {
        e.valor.inteiro = 100;
        cout << "Inteiro: " << e.valor.inteiro << endl;
    } else {
        e.valor.decimal = 50.5;
        cout << "Decimal: " << e.valor.decimal << endl;
    }

    return 0;
}
```

## Explicação
### Armadilhas Comuns
1. **Sobrescrita de Memória**: Apenas um membro da `union` pode ser acessado de cada vez. Quando um novo valor é atribuído a um membro, o valor anterior é perdido. Isso pode levar a comportamentos inesperados se não for manuseado corretamente.
   
2. **Tamanho da União**: O tamanho de uma `union` é determinado pelo tamanho do maior membro. Isso pode ser contraintuitivo para novos programadores.

3. **Inicialização**: É importante inicializar a `union` corretamente. A melhor prática é usar um membro ao inicializar a `union`, pois o valor dos outros membros será indeterminado.

4. **Acesso a Membros Inativos**: Acessar um membro que não foi mais atribuído após a última modificação pode resultar em comportamento indefinido.

## Resumo em Uma Linha
A `union` em C++ é uma estrutura que permite armazenar diferentes tipos de dados em um único espaço de memória, mas apenas um membro pode ser usado por vez.