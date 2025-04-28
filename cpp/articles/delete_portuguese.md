<!--
Meta Description: # Comando "delete" em C++ ## Sinopse O comando `delete` em C++ é utilizado para liberar a memória alocada dinamicamente para objetos ou variáveis, evi...
Meta Keywords: delete, memória, que, para, new
-->

# Comando "delete" em C++

## Sinopse
O comando `delete` em C++ é utilizado para liberar a memória alocada dinamicamente para objetos ou variáveis, evitando vazamentos de memória e garantindo a eficiência da aplicação.

## Documentação
O `delete` é um operador em C++ que serve para desalocar a memória previamente alocada com o operador `new`. É crucial em programas que utilizam alocação dinâmica, pois libera recursos que não são mais necessários.

### Finalidade
O objetivo do `delete` é evitar o desperdício de memória e garantir que os recursos do sistema sejam gerenciados de forma eficaz.

### Uso
O `delete` pode ser utilizado de duas maneiras:

1. Para objetos alocados individualmente:
   ```cpp
   delete ponteiro;
   ```

2. Para arrays de objetos alocados com `new[]`:
   ```cpp
   delete[] ponteiro;
   ```

### Detalhes
- O operador `delete` deve ser chamado apenas em ponteiros que foram alocados com `new`. Chamar `delete` em ponteiros que não foram alocados com `new` ou que já foram deletados resulta em comportamento indefinido.
- Após a chamada de `delete`, é uma boa prática definir o ponteiro como `nullptr` para evitar referências a memória que já foi liberada.

## Exemplos
### Exemplo 1: Uso básico do `delete`
```cpp
#include <iostream>

class Exemplo {
public:
    Exemplo() { std::cout << "Construtor chamado" << std::endl; }
    ~Exemplo() { std::cout << "Destrutor chamado" << std::endl; }
};

int main() {
    Exemplo* obj = new Exemplo(); // Alocação dinâmica
    delete obj; // Liberação da memória
    return 0;
}
```

### Exemplo 2: Uso de `delete[]`
```cpp
#include <iostream>

int main() {
    int* array = new int[5]; // Alocação de um array
    delete[] array; // Liberação da memória do array
    return 0;
}
```

## Explicação
### Armadilhas Comuns
- **Chamar `delete` em ponteiros não alocados com `new`**: Isso causa comportamento indefinido, podendo levar a falhas de segmentação.
- **Não usar `delete`**: Deixar de liberar memória alocada pode causar vazamentos de memória, especialmente em programas de longa execução.
- **Deletar ponteiros múltiplas vezes**: Tentar deletar um ponteiro que já foi deletado (ou que não foi inicializado) resulta em comportamento indefinido.

### Notas Adicionais
- É recomendável utilizar smart pointers (como `std::unique_ptr` e `std::shared_ptr`) em C++ moderno para gerenciar a memória automaticamente, reduzindo o risco de erros relacionados à memória.

## Resumo em Uma Linha
O operador `delete` em C++ é utilizado para liberar a memória alocada dinamicamente, evitando vazamentos e garantindo a eficiência do gerenciamento de recursos.