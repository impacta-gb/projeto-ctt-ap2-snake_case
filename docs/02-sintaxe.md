# 🧠 Fundamentos da Linguagem Go

> Conhecendo os conceitos básicos da linguagem Go e os elementos essenciais para iniciar o desenvolvimento de aplicações modernas.

---

# 👋 Hello World em Go

O tradicional programa **Hello World** demonstra a estrutura básica de uma aplicação Go.

Ele é utilizado para:

* ✅ aprender a sintaxe inicial
* ✅ entender a estrutura do código
* ✅ testar o ambiente de desenvolvimento
* ✅ executar o primeiro programa

---

# 💻 Exemplo de Hello World

```go id="8r4e2f"
package main

import "fmt"

func main() {
    fmt.Println("Hello World")
}
```

---

# 📦 Estrutura do programa

| Elemento        | Função                                |
| --------------- | ------------------------------------- |
| `package main`  | Define o pacote principal             |
| `import "fmt"`  | Importa funcionalidades de formatação |
| `func main()`   | Função principal da aplicação         |
| `fmt.Println()` | Exibe texto no terminal               |

---

# ▶️ Executando o programa

```go id="nzzj5p"
go run main.go
```

> 🚀 Esse é normalmente o primeiro programa criado ao aprender Go.

---

# ⚙️ Comando go

O comando `go` é a principal ferramenta para gerenciamento do ecossistema Go.

Ele automatiza grande parte do fluxo de desenvolvimento.

---

# 🛠️ Principais funcionalidades

* ✅ compilar projetos
* ✅ executar aplicações
* ✅ rodar testes
* ✅ formatar código
* ✅ gerenciar dependências

---

# 📚 Principais comandos

| Comando    | Função                |
| ---------- | --------------------- |
| `go run`   | Executa programas     |
| `go build` | Compila o projeto     |
| `go test`  | Executa testes        |
| `go fmt`   | Formata código        |
| `go mod`   | Gerencia dependências |

---

# 💻 Exemplos

```go id="6svyrw"
go build
go test
go fmt
```

---

# 📦 Variáveis e Constantes

Variáveis armazenam valores que podem ser alterados durante a execução do programa.

Constantes armazenam valores fixos definidos em tempo de compilação.

---

# 🔄 Declarando variáveis

## Utilizando var

```go id="d78shh"
var nome string = "Maria"
```

---

## Utilizando inferência de tipo

```go id="2ijhfd"
idade := 25
```

> 💡 O operador `:=` permite que o Go descubra automaticamente o tipo da variável.

---

# 🔒 Declarando constantes

```go id="bngt84"
const PI = 3.14
```

---

# 📊 Variáveis vs Constantes

| Recurso    | Característica         |
| ---------- | ---------------------- |
| Variáveis  | Valores alteráveis     |
| Constantes | Valores imutáveis      |
| `var`      | Declaração tradicional |
| `:=`       | Inferência automática  |

---

# 🧠 Valores Zero

Variáveis não inicializadas recebem automaticamente valores padrão chamados de:

> **Valores zero**

---

# 📋 Valores padrão

| Tipo      | Valor zero |
| --------- | ---------- |
| Números   | `0`        |
| Booleanos | `false`    |
| Strings   | `""`       |
| Pointers  | `nil`      |
| Slices    | `nil`      |
| Maps      | `nil`      |

---

# 💻 Exemplo

```go id="m0wbto"
var numero int

fmt.Println(numero)
```

Saída:

```text id="1y72yt"
0
```

> 💡 Isso garante um estado inicial previsível e reduz erros de inicialização.

---

# 🔢 const e iota

Constantes declaradas com `const` representam valores fixos em tempo de compilação.

O `iota` cria constantes inteiras sequenciais automaticamente.

---

# 💻 Exemplo com iota

```go id="sgrb83"
const (
    Domingo = iota
    Segunda
    Terca
    Quarta
)
```

---

# 📊 Resultado do iota

| Constante | Valor |
| --------- | ----- |
| Domingo   | 0     |
| Segunda   | 1     |
| Terca     | 2     |
| Quarta    | 3     |

---

# 🚀 Onde o iota é utilizado?

* ✅ enumerações
* ✅ flags
* ✅ sequências automáticas
* ✅ controle de estados

---

# 🌍 Escopo

Escopo determina onde uma variável pode ser acessada dentro do programa.

Go possui:

| Tipo de escopo   | Descrição          |
| ---------------- | ------------------ |
| Escopo de pacote | Variáveis globais  |
| Escopo de função | Variáveis locais   |
| Escopo de bloco  | Variáveis internas |

---

# ⚠️ Shadowing

Shadowing ocorre quando uma variável em um escopo interno possui o mesmo nome de outra variável em um escopo externo.

Nesse caso, a variável interna “esconde” temporariamente a original.

---

# 💻 Exemplo de Shadowing

```go id="mpvq5s"
nome := "Maria"

if true {
    nome := "Carlos"

    fmt.Println(nome)
}
```

> ⚠️ Shadowing excessivo pode causar bugs difíceis de identificar.

---

# 🚨 Cuidados importantes

> ⚠️ Variáveis globais em excesso dificultam manutenção e testes.

> 🚨 Shadowing pode gerar comportamentos inesperados.

> 💡 Prefira escopos menores e variáveis bem definidas.

---

# 🎯 Benefícios desses conceitos

* ✅ Código mais organizado
* ✅ Melhor legibilidade
* ✅ Maior previsibilidade
* ✅ Menor risco de erros
* ✅ Desenvolvimento mais seguro

---

# 📊 Resumo rápido

| Conceito   | Objetivo               |
| ---------- | ---------------------- |
| `main()`   | Ponto de entrada       |
| `go`       | Ferramenta principal   |
| Variáveis  | Valores mutáveis       |
| Constantes | Valores fixos          |
| `iota`     | Sequências automáticas |
| Escopo     | Controle de acesso     |

---

# ✅ Conclusão

Os fundamentos da linguagem Go são essenciais para construir aplicações modernas, eficientes e confiáveis.

Compreender variáveis, constantes, escopo, valores zero e o funcionamento do comando `go` é o primeiro passo para evoluir no ecossistema da linguagem.
