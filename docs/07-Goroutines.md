# Goroutines

## O que são Goroutines?

Goroutines são threads leves gerenciadas pelo runtime da linguagem Go que permitem a execução concorrente de funções.

Elas são uma das funcionalidades mais poderosas da linguagem, tornando simples a criação de programas concorrentes e paralelos.

---

## Criando uma Goroutine

Uma goroutine é criada utilizando a palavra-chave `go` antes da chamada de uma função.

### Exemplo simples

```go
go minhaFuncao()
```

---

## Exemplo completo

```go
package main

import (
    "fmt"
    "time"
)

func mensagem() {
    fmt.Println("Executando goroutine")
}

func main() {
    go mensagem()

    time.Sleep(time.Second)
}
```

!!! note "Importante"
O `time.Sleep()` é utilizado neste exemplo para evitar que o programa principal finalize antes da execução da goroutine.

---

## Características das Goroutines

As goroutines possuem baixo consumo de memória e podem ser criadas em grande quantidade, permitindo que milhares ou até milhões delas executem simultaneamente.

O runtime do Go é responsável pelo gerenciamento e escalonamento automático entre os núcleos da CPU.

| Característica           | Descrição                                     |
| ------------------------ | --------------------------------------------- |
| Leves                    | Consomem pouca memória                        |
| Concorrentes             | Executam tarefas simultaneamente              |
| Escaláveis               | Permitem milhares de execuções                |
| Gerenciadas pelo runtime | O Go controla automaticamente o escalonamento |

---

## Boas práticas

!!! tip "Boa prática"
Utilize goroutines para tarefas concorrentes como servidores web, processamento paralelo e operações de rede.

!!! tip "Dica"
Prefira dividir tarefas independentes em goroutines menores para melhorar a organização do código.

---

## Diferença entre Goroutines e Threads

Diferente das threads tradicionais dos sistemas operacionais, as goroutines são mais leves e eficientes, pois o próprio runtime da linguagem controla sua execução.

| Threads tradicionais                 | Goroutines                  |
| ------------------------------------ | --------------------------- |
| Gerenciadas pelo sistema operacional | Gerenciadas pelo runtime Go |
| Alto consumo de memória              | Baixo consumo de memória    |
| Mais pesadas                         | Mais leves                  |
| Menor escalabilidade                 | Alta escalabilidade         |

---

## Comunicação entre Goroutines

As goroutines normalmente se comunicam através de channels, seguindo o princípio:

> “Não compartilhe memória diretamente; compartilhe memória através da comunicação.”

---

## Cuidados importantes

!!! warning "Cuidado"
Criar muitas goroutines sem controle pode causar consumo excessivo de recursos e dificultar a sincronização das tarefas.

!!! danger "Atenção"
Goroutines mal sincronizadas podem gerar race conditions e comportamentos inesperados na aplicação.

---

## Conclusão

A concorrência em Go facilita o desenvolvimento de aplicações modernas e escaláveis, especialmente em sistemas distribuídos, APIs e aplicações de alto desempenho.

As goroutines tornam o desenvolvimento concorrente mais simples, eficiente e seguro quando utilizadas corretamente.
