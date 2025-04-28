<!--
Meta Description: # mutable em C++: Entenda o Modificador para Membros de Estruturas e Classes ## Sinopse O `mutable` é um modificador em C++ que permite a um membro de...
Meta Keywords: mutable, cache, que, const, não
-->

# mutable em C++: Entenda o Modificador para Membros de Estruturas e Classes

## Sinopse
O `mutable` é um modificador em C++ que permite a um membro de estrutura ou classe ser modificado mesmo quando a instância da classe é declarada como `const`. Isso é útil para situações em que você precisa manter informações auxiliares que não fazem parte do estado lógico do objeto.

## Documentação
O `mutable` é usado principalmente para membros de classes e estruturas em C++. Quando um membro de dados é declarado como `mutable`, ele pode ser modificado mesmo em métodos que são marcados como `const`. 

### Propósito
O propósito do `mutable` é permitir a modificação de dados que não devem alterar a "interface pública" do objeto. Por exemplo, você pode querer armazenar um valor de cache em um objeto que, de outra forma, não pode ser alterado.

### Uso
Para utilizar o `mutable`, basta declará-lo antes do membro que você deseja tornar mutável. Aqui está a sintaxe básica:

```cpp
class MinhaClasse {
public:
    mutable int contador; // Membro mutável

    MinhaClasse() : contador(0) {}

    void incrementar() const {
        contador++; // Pode ser modificado em um método const
    }
};
```

### Detalhes
- Um membro `mutable` não altera a constância do objeto; o objeto ainda é considerado `const` se for declarado como tal.
- É comum usar `mutable` para implementar caches ou contadores que não devem afetar a lógica de estado do objeto.

## Exemplos
Aqui estão alguns exemplos simples que mostram como usar o `mutable` em C++:

### Exemplo 1: Uso Básico
```cpp
#include <iostream>

class Contador {
public:
    mutable int count; // Membro mutável

    Contador() : count(0) {}

    void incrementar() const {
        count++; // Modificação permitida
    }
};

int main() {
    const Contador c;
    c.incrementar(); // Isso é válido
    std::cout << "Contador: " << c.count << std::endl; // Saída: Contador: 1
    return 0;
}
```

### Exemplo 2: Uso com Cache
```cpp
#include <iostream>

class Fatorial {
public:
    mutable int cache; // Membro mutável
    int n;

    Fatorial(int num) : n(num), cache(-1) {}

    int calcular() const {
        if (cache != -1) {
            return cache; // Retorna o valor em cache
        }
        cache = 1;
        for (int i = 1; i <= n; i++) {
            cache *= i;
        }
        return cache; // Armazena o resultado em cache
    }
};

int main() {
    const Fatorial f(5);
    std::cout << "Fatorial: " << f.calcular() << std::endl; // Saída: Fatorial: 120
    std::cout << "Cache: " << f.cache << std::endl; // Saída: Cache: 120
    return 0;
}
```

## Explicação
Um dos principais erros ao usar `mutable` é não compreender que apenas o membro mutável pode ser alterado. Outros membros ou métodos que não são declarados como `mutable` não podem ser modificados em um contexto `const`. 

Além disso, o uso excessivo de `mutable` pode levar a um design confuso, onde a separação entre o que é mutável e imutável não é clara. É essencial usar esse modificador com cautela e apenas quando necessário.

## Resumo em uma Linha
O `mutable` em C++ permite que membros de classes ou estruturas sejam modificados mesmo em métodos `const`, facilitando a implementação de caches e contadores.