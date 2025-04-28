<!--
Meta Description: # A palavra-chave "explicit" em C++ ## Sinopse A palavra-chave `explicit` é usada em C++ para evitar conversões implícitas indesejadas em construtores...
Meta Keywords: explicit, conversão, exemplo, valor, não
-->

# A palavra-chave "explicit" em C++

## Sinopse
A palavra-chave `explicit` é usada em C++ para evitar conversões implícitas indesejadas em construtores e operadores de conversão, garantindo que a conversão de tipos ocorra apenas quando explicitamente solicitada.

## Documentação
A palavra-chave `explicit` é aplicada a construtores de uma classe e a operadores de conversão. Seu principal objetivo é prevenir a criação acidental de objetos por meio de conversões implícitas, que podem levar a comportamentos inesperados ou a erros sutis no código.

### Propósito
O uso de `explicit` ajuda a melhorar a legibilidade do código e a segurança de tipos. Quando um construtor é marcado como `explicit`, ele não pode ser chamado com um único argumento em um contexto onde uma conversão implícita poderia ocorrer.

### Uso
Para declarar um construtor como `explicit`, basta precedê-lo com a palavra-chave `explicit`. Aqui está um exemplo básico:

```cpp
class Exemplo {
public:
    explicit Exemplo(int valor) {
        // Inicialização
    }
};
```

Neste exemplo, o construtor `Exemplo(int valor)` só pode ser chamado explicitamente, prevenindo que um inteiro seja convertido automaticamente em um objeto `Exemplo`.

### Detalhes
- Construtores `explicit` podem ser chamados explicitamente:
  ```cpp
  Exemplo obj(10);  // Correto
  Exemplo obj2 = 10; // Errado: conversão implícita não permitida
  ```
- A palavra-chave `explicit` pode ser usada com operadores de conversão:
  ```cpp
  class OutraClasse {
  public:
      explicit operator int() {
          return 42;
      }
  };
  ```

## Exemplos

### Exemplo 1: Uso Básico
```cpp
class Inteiro {
public:
    explicit Inteiro(int valor) : valor(valor) {}
private:
    int valor;
};

int main() {
    Inteiro i1(5); // Correto
    // Inteiro i2 = 5; // Errado: conversão implícita não permitida
}
```

### Exemplo 2: Operador de Conversão
```cpp
class String {
public:
    explicit String(const char* str) : valor(str) {}

    explicit operator const char*() const {
        return valor.c_str();
    }
private:
    std::string valor;
};

int main() {
    String s("Hello");
    const char* cstr = (const char*)s; // Correto: conversão explícita
    // const char* cstr2 = s; // Errado: conversão implícita não permitida
}
```

## Explicação
Um dos principais problemas ao não usar `explicit` é a possibilidade de conversões implícitas ocorrerem em situações que não são desejadas, levando a erros difíceis de detectar. Por exemplo, ao passar parâmetros para funções que esperam tipos diferentes, o compilador pode tentar fazer uma conversão implícita, resultando em comportamento indefinido.

### Armadilhas Comuns
- **Conversões indesejadas**: Ao não usar `explicit`, você corre o risco de que conversões automáticas ocorram, o que pode não ser intuitivo.
- **Dificuldades de depuração**: Erros resultantes de conversões automáticas podem ser difíceis de identificar, especialmente em grandes projetos.

## Resumo em Uma Linha
A palavra-chave `explicit` em C++ é usada para evitar conversões implícitas indesejadas em construtores e operadores de conversão, promovendo um código mais seguro e legível.