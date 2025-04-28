<!--
Meta Description: # A palavra-chave "extern" em C++: Entendendo seu Uso e Aplicações ## Sinopse A palavra-chave `extern` em C++ é utilizada para declarar uma variável o...
Meta Keywords: extern, que, variável, cpp, arquivo
-->

# A palavra-chave "extern" em C++: Entendendo seu Uso e Aplicações

## Sinopse
A palavra-chave `extern` em C++ é utilizada para declarar uma variável ou função que está definida em outro arquivo ou módulo. Essa declaração permite que o linker encontre a definição real no momento da ligação.

## Documentação
A palavra-chave `extern` tem um papel fundamental na programação em C++, especialmente em projetos que envolvem múltiplos arquivos de código fonte. Seu propósito principal é permitir a visibilidade de variáveis e funções que são definidas fora do escopo atual.

### Propósito
- **Visibilidade Global**: `extern` é usado para indicar que uma variável ou função não é local ao arquivo atual, mas sim acessível em outros arquivos.
- **Organização de Código**: Facilita a modularização do código, permitindo que diferentes partes de um programa sejam divididas em arquivos separados.

### Uso
A declaração `extern` pode ser aplicada a variáveis e funções. A sintaxe básica é a seguinte:

```cpp
extern tipo nome_variavel;
extern tipo nome_funcao(parametros);
```

### Detalhes
- Para variáveis, `extern` informa ao compilador que a variável está definida em outro lugar, e não no arquivo atual. É comum usar essa palavra-chave em arquivos de cabeçalho (.h) para que a variável possa ser compartilhada entre vários arquivos de implementação (.cpp).
- Para funções, a declaração `extern` é implicitamente aplicada, já que todas as funções têm linkage externo por padrão, a menos que sejam declaradas como `static`.

## Exemplos

### Exemplo 1: Variável Externa

**Arquivo: main.cpp**
```cpp
#include <iostream>
extern int contador; // Declaração da variável externa

int main() {
    std::cout << "Contador: " << contador << std::endl;
    return 0;
}
```

**Arquivo: contador.cpp**
```cpp
int contador = 10; // Definição da variável externa
```

### Exemplo 2: Função Externa

**Arquivo: main.cpp**
```cpp
#include <iostream>
extern void mostrarMensagem(); // Declaração da função externa

int main() {
    mostrarMensagem();
    return 0;
}
```

**Arquivo: func.cpp**
```cpp
#include <iostream>
void mostrarMensagem() {
    std::cout << "Olá, mundo!" << std::endl;
}
```

## Explicação
Um erro comum ao usar `extern` é esquecer de incluir o arquivo de cabeçalho que contém a declaração da variável ou função. Isso pode resultar em erros de compilação, como "variável não declarada". Além disso, é importante lembrar que `extern` não inicializa a variável; ele apenas declara sua existência em outro lugar.

Outro ponto a considerar é que, ao usar `extern`, não se deve redeclarar a variável com a palavra-chave `extern` em um escopo onde ela já foi definida, pois isso pode causar confusão.

## Resumo em Uma Linha
A palavra-chave `extern` em C++ permite a declaração de variáveis e funções que são definidas em outros arquivos, facilitando a modularização e a organização do código.