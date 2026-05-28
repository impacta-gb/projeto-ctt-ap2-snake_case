# ⚠️ Tratamento de Erros em Go

> Construindo aplicações mais seguras, previsíveis e confiáveis através do tratamento explícito de erros.

---

## 📌 O que é o tratamento de erros em Go?

Go utiliza um sistema de tratamento de erros explícito baseado em valores de retorno do tipo `error`.

Diferente de linguagens que utilizam exceções automáticas, em Go os erros devem ser verificados manualmente pelo programador.

Essa abordagem torna o fluxo do programa:

* ✅ mais previsível
* ✅ mais simples de entender
* ✅ mais seguro
* ✅ mais fácil de manter

---

# 🔍 Verificando erros

Normalmente, as funções retornam o erro como o último valor de retorno.

O padrão mais utilizado para verificar falhas é:

```go
if err != nil {
    // tratamento do erro
}
```

> 💡 Em Go, ignorar erros é considerado uma má prática.

---

# 💻 Exemplo completo

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    arquivo, err := os.Open("dados.txt")

    if err != nil {
        fmt.Println("Erro ao abrir arquivo:", err)
        return
    }

    defer arquivo.Close()

    fmt.Println("Arquivo aberto com sucesso")
}
```

---

# 📦 Como funciona o exemplo?

| Etapa                   | Função                          |
| ----------------------- | ------------------------------- |
| `os.Open()`             | Tenta abrir o arquivo           |
| `err`                   | Armazena possível erro          |
| `if err != nil`         | Verifica falha                  |
| `defer arquivo.Close()` | Fecha o arquivo automaticamente |

---

# 🛠️ Criando erros personalizados

Go oferece a função:

```go
errors.New()
```

para criar erros personalizados.

## Exemplo

```go
err := errors.New("erro personalizado")
```

---

# ✨ Mensagens formatadas

Também é possível utilizar:

```go
fmt.Errorf()
```

para criar mensagens de erro formatadas.

## Exemplo

```go
err := fmt.Errorf("falha ao conectar no servidor")
```

> 🚀 `fmt.Errorf()` é muito útil para adicionar contexto aos erros.

---

# ⚠️ Cuidados importantes

> ⚠️ Ignorar erros pode causar comportamentos inesperados e dificultar a manutenção do sistema.

> 🚨 Erros não tratados podem comprometer a estabilidade da aplicação.

> 💡 Sempre valide possíveis falhas em operações críticas como arquivos, APIs e banco de dados.

---

# ❌ Exceções em Go

Go não possui tratamento tradicional de exceções como:

```text
try/catch
```

Em vez disso, os erros são tratados como valores comuns que devem ser verificados explicitamente.

Essa abordagem incentiva:

* ✅ código mais claro
* ✅ maior previsibilidade
* ✅ menos comportamentos ocultos

---

# 🔥 Panic e Recover

Além do tratamento tradicional de erros, Go também possui os mecanismos:

| Recurso   | Função                            |
| --------- | --------------------------------- |
| `panic`   | Interrompe a execução do programa |
| `recover` | Recupera um panic                 |

---

## 💻 Exemplo de panic

```go
panic("erro crítico")
```

> 🚨 O `panic` deve ser utilizado apenas em situações críticas e inesperadas.

---

# 🧩 Quando usar panic?

O uso de `panic` é recomendado em casos como:

* falhas irreversíveis
* corrupção de memória
* erros críticos do sistema
* situações impossíveis de recuperar

---

# 🎯 Benefícios do tratamento explícito

* ✅ Código mais previsível
* ✅ Facilidade de manutenção
* ✅ Maior confiabilidade
* ✅ Menor risco de falhas silenciosas
* ✅ Melhor controle da aplicação

---

# 📊 Resumo rápido

| Recurso         | Objetivo                  |
| --------------- | ------------------------- |
| `error`         | Representa erros          |
| `if err != nil` | Verifica falhas           |
| `errors.New()`  | Cria erros personalizados |
| `fmt.Errorf()`  | Formata mensagens         |
| `panic`         | Interrompe execução       |
| `recover`       | Recupera panic            |

---

# ✅ Conclusão

O tratamento de erros é uma das características mais importantes da linguagem Go.

A abordagem explícita adotada pela linguagem contribui para a criação de aplicações:

* seguras,
* robustas,
* previsíveis,
* e fáceis de manter.
