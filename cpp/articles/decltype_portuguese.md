<!--
Meta Description: # decltype: Entendendo o Tipo de Declaração em C++ ## Sinopse O `decltype` é uma palavra-chave fundamental em C++ que permite determinar o tipo de uma...
Meta Keywords: decltype, tipo, expressão, uma, int
-->

# decltype: Entendendo o Tipo de Declaração em C++

## Sinopse
O `decltype` é uma palavra-chave fundamental em C++ que permite determinar o tipo de uma expressão em tempo de compilação, facilitando a criação de código mais genérico e seguro. 

## Documentação
### Propósito
O `decltype` é utilizado para inferir o tipo de uma variável ou expressão sem a necessidade de definir explicitamente esse tipo. Isso é particularmente útil em contextos onde o tipo pode ser complexo ou dependente de outras variáveis.

### Uso
A sintaxe básica do `decltype` é:

```cpp
decltype(expressão)
```

Aqui, `expressão` pode ser qualquer expressão válida em C++. O compilador então deduz o tipo resultante dessa expressão.

### Detalhes
- `decltype` pode ser utilizado em variáveis, funções, e até em tipos de retorno.
- Se a expressão passada a `decltype` é uma variável, o tipo resultante é o mesmo que o tipo da variável. Se a expressão é uma chamada de função, o tipo resultante será o tipo de retorno da função.
- O `decltype` pode ser combinado com `auto` para criar tipos mais complexos e flexíveis.

## Exemplos
### Exemplo Básico
```cpp
#include <iostream>
#include <vector>

int main() {
    int a = 5;
    decltype(a) b = 10; // b é do tipo int

    std::cout << "Valor de b: " << b << std::endl;

    std::vector<int> vec = {1, 2, 3};
    decltype(vec) vec2 = vec; // vec2 é um std::vector<int>

    std::cout << "Tamanho de vec2: " << vec2.size() << std::endl;

    return 0;
}
```

### Exemplo Avançado
```cpp
#include <iostream>
#include <type_traits>

template<typename T>
decltype(auto) retornaTipo(T t) {
    return t;
}

int main() {
    auto resultado = retornaTipo(5); // resultado é do tipo int
    std::cout << "Tipo de resultado é int? " << std::is_same<decltype(resultado), int>::value << std::endl;

    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Expressões Lvalue e Rvalue**: O `decltype` mantém a categoria de valor da expressão. Se você usar uma variável, o tipo resultante será um lvalue. Isso pode causar confusão se a intenção for obter um rvalue. 
- **Expressões não válidas**: Se a expressão passada para `decltype` não for válida, o compilador gerará um erro. É importante garantir que a expressão seja legível e válida em qualquer contexto.

### Notas Adicionais
- O uso de `decltype` é especialmente vantajoso em templates e funções de alta ordem, onde os tipos podem ser difíceis de definir.
- Com a introdução de C++11, o `decltype` se tornou uma ferramenta poderosa para programação genérica.

## Resumo em Uma Linha
O `decltype` em C++ é uma palavra-chave que permite inferir o tipo de uma expressão em tempo de compilação, promovendo um código mais flexível e seguro.