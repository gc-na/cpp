<!--
Meta Description: # thread_local em C++: Entenda a Memória Local de Thread ## Sinopse O `thread_local` é um especificador de armazenamento em C++ que permite que variáv...
Meta Keywords: thread, thread_local, que, contador, variável
-->

# thread_local em C++: Entenda a Memória Local de Thread

## Sinopse
O `thread_local` é um especificador de armazenamento em C++ que permite que variáveis tenham uma instância única para cada thread, garantindo que cada thread mantenha seu próprio estado sem interferir nas outras.

## Documentação
O especificador `thread_local` foi introduzido no C++11 e é utilizado para declarar variáveis que serão únicas para cada thread. Isso significa que cada thread que acessa uma variável `thread_local` terá sua própria cópia, o que é essencial para evitar condições de corrida e garantir a segurança do acesso a dados em ambientes multithread.

### Propósito
O principal objetivo do `thread_local` é proteger dados que serão acessados simultaneamente por várias threads, permitindo que cada thread mantenha uma cópia independente da variável.

### Uso
Para declarar uma variável como `thread_local`, basta prefixar a palavra-chave `thread_local` antes do tipo da variável. Essa variável pode ser estática ou não estática, mas a forma estática é mais comum.

**Exemplo de declaração:**
```cpp
thread_local int contador = 0;
```

### Detalhes
- Cada thread inicializa sua própria cópia da variável quando a thread é criada.
- O destrutor da variável `thread_local` é chamado automaticamente quando a thread termina.
- Variáveis `thread_local` podem ser usadas em funções, classes, e em qualquer escopo onde variáveis normais podem ser declaradas.
- `thread_local` não é aplicável a tipos de dados que não suportam construção e destruição, como ponteiros para funções.

## Exemplos
Aqui estão alguns exemplos básicos que demonstram o uso de `thread_local`:

### Exemplo 1: Contador de Thread
```cpp
#include <iostream>
#include <thread>

thread_local int contador = 0;

void incrementar() {
    for (int i = 0; i < 5; ++i) {
        contador++;
        std::cout << "Thread " << std::this_thread::get_id() << " contador: " << contador << std::endl;
    }
}

int main() {
    std::thread t1(incrementar);
    std::thread t2(incrementar);

    t1.join();
    t2.join();

    return 0;
}
```
**Saída esperada:**
```
Thread 139896712102464 contador: 1
Thread 139896703709760 contador: 1
Thread 139896712102464 contador: 2
Thread 139896703709760 contador: 2
...
```

### Exemplo 2: Variável Thread-Local em Classe
```cpp
#include <iostream>
#include <thread>

class Exemplo {
public:
    void incrementar() {
        for (int i = 0; i < 5; ++i) {
            contador++;
            std::cout << "Thread " << std::this_thread::get_id() << " contador: " << contador << std::endl;
        }
    }

private:
    thread_local static int contador;
};

thread_local int Exemplo::contador = 0;

int main() {
    Exemplo exemplo;
    std::thread t1(&Exemplo::incrementar, &exemplo);
    std::thread t2(&Exemplo::incrementar, &exemplo);

    t1.join();
    t2.join();

    return 0;
}
```

## Explicação
Embora o uso de `thread_local` possa facilitar a programação multithread, existem algumas armadilhas comuns que os desenvolvedores devem estar cientes:

- **Desempenho**: O uso excessivo de variáveis `thread_local` pode afetar o desempenho devido à sobrecarga de gerenciamento de memória por thread.
- **Destrutores**: Os destrutores das variáveis `thread_local` são chamados quando a thread termina, portanto, o acesso à variável após o término da thread pode levar a comportamentos indefinidos.
- **Inicialização**: A variável `thread_local` é inicializada na primeira vez que a thread a acessa, o que pode causar atraso em threads que a utilizam pela primeira vez.

## Resumo em Uma Linha
O `thread_local` em C++ permite que cada thread tenha sua própria instância de uma variável, promovendo segurança e independência em ambientes multithread.