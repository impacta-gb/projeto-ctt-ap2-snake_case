# 🔄 Channels

> Comunicação segura entre goroutines utilizando concorrência em Go.

---

## 📌 O que são Channels?

Channels são o principal mecanismo de comunicação entre goroutines em Go.

Eles permitem enviar e receber dados entre tarefas concorrentes de forma segura, seguindo o princípio:

> “Compartilhe memória através da comunicação.”

---

# 🛠️ Criando um Channel

Os channels são tipados e criados utilizando a função `make()`.

## Exemplo básico

```go
canal := make(chan int)
```

> ℹ️ O exemplo acima cria um channel capaz de armazenar apenas valores do tipo `int`.

---

# 💻 Enviando e recebendo dados

Os channels permitem troca segura de informações entre goroutines.

## Exemplo completo

```go
package main

import "fmt"

func main() {
    canal := make(chan string)

    go func() {
        canal <- "Olá Goroutine"
    }()

    mensagem := <-canal

    fmt.Println(mensagem)
}
```

---

# 📚 Operações principais

| Operação         | Função                     |
| ---------------- | -------------------------- |
| `canal <- valor` | Envia dados para o channel |
| `<-canal`        | Recebe dados do channel    |
| `close(canal)`   | Fecha o channel            |

---

# 📦 Tipos de Channels

Os channels podem ser classificados em dois tipos:

| Tipo          | Característica                            |
| ------------- | ----------------------------------------- |
| 🔹 Sem buffer | Espera envio e recebimento simultâneo     |
| 🔸 Com buffer | Permite armazenar valores temporariamente |

---

# 🧠 Channel com buffer

Channels com buffer permitem armazenar valores antes que outra goroutine faça a leitura.

## Exemplo

```go
canal := make(chan int, 2)
```

> 💡 No exemplo acima, o channel suporta até 2 valores temporariamente.

---

# 🚀 Principais usos dos Channels

Channels são amplamente utilizados para:

* ✅ Sincronização entre goroutines
* ✅ Comunicação segura de dados
* ✅ Coordenação de tarefas concorrentes
* ✅ Controle de execução

---

# ⚠️ Cuidados importantes

> ⚠️ Channels mal utilizados podem causar deadlocks na aplicação.

> 🚨 Fechar um channel já fechado gera panic.

> ℹ️ Channels ajudam a evitar problemas comuns de concorrência, como race conditions.

---

# 🔒 Fechando um Channel

Também é possível utilizar o comando `close()` para encerrar um channel quando ele não será mais utilizado.

## Exemplo

```go
close(canal)
```

> 💡 Feche channels apenas quando tiver certeza de que nenhum outro valor será enviado.

---

# 📊 Benefícios dos Channels

| Benefício         | Descrição                             |
| ----------------- | ------------------------------------- |
| 🚀 Escalabilidade | Melhor aproveitamento da concorrência |
| 🔐 Segurança      | Menor risco de race conditions        |
| ⚡ Eficiência      | Baixo consumo de recursos             |
| 🧩 Organização    | Código concorrente mais limpo         |

---

# ✅ Conclusão

A combinação de goroutines e channels torna Go uma linguagem extremamente poderosa para desenvolvimento concorrente.

Os channels permitem criar aplicações:

* modernas,
* eficientes,
* escaláveis,
* seguras,
* e mais fáceis de manter.
