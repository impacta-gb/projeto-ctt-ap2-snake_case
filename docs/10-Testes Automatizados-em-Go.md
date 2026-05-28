# 🧪 Testes Automatizados em Go

> Garantindo qualidade, confiabilidade e segurança no desenvolvimento de aplicações Go.

---

## 📌 O que são testes automatizados?

A linguagem Go possui suporte nativo para testes automatizados através do pacote `testing`.

Os testes são fundamentais para:

* ✅ garantir o funcionamento correto do código
* ✅ reduzir bugs
* ✅ facilitar manutenção
* ✅ aumentar a confiabilidade do sistema
* ✅ validar alterações futuras

---

# 📂 Estrutura dos testes em Go

Os arquivos de teste em Go devem possuir o sufixo:

```text
_test.go
```

As funções de teste devem começar com a palavra:

```text
Test
```

---

# 💻 Exemplo de teste simples

```go
package main

import "testing"

func Soma(a int, b int) int {
    return a + b
}

func TestSoma(t *testing.T) {
    resultado := Soma(2, 3)

    if resultado != 5 {
        t.Errorf("Esperado 5, mas recebeu %d", resultado)
    }
}
```

> 💡 O pacote `testing` é responsável por fornecer as ferramentas necessárias para execução e validação dos testes.

---

# ▶️ Executando testes

Para executar os testes do projeto, utiliza-se o comando:

```go
go test
```

---

## 🔍 Execução detalhada

Caso seja necessário visualizar mais informações sobre os testes:

```go
go test -v
```

| Comando      | Função                     |
| ------------ | -------------------------- |
| `go test`    | Executa os testes          |
| `go test -v` | Exibe detalhes da execução |

---

# 📊 Table-Driven Tests

Uma prática muito comum em Go é a utilização de:

> **Table-Driven Tests**

Essa técnica permite testar múltiplos cenários de forma organizada e reduz a repetição de código.

---

## 💻 Exemplo

```go
func TestSomaTabela(t *testing.T) {
    testes := []struct {
        a, b int
        esperado int
    }{
        {1, 2, 3},
        {2, 3, 5},
        {10, 5, 15},
    }

    for _, teste := range testes {
        resultado := Soma(teste.a, teste.b)

        if resultado != teste.esperado {
            t.Errorf("Esperado %d, recebeu %d",
                teste.esperado, resultado)
        }
    }
}
```

> 🚀 Table-driven tests tornam os testes mais organizados, reutilizáveis e fáceis de manter.

---

# 🧩 Mocks e Stubs

Go também permite o uso de:

* ✅ mocks
* ✅ stubs

Esses recursos são utilizados para simular dependências externas como:

| Dependência    | Exemplo              |
| -------------- | -------------------- |
| APIs           | Serviços externos    |
| Banco de dados | Consultas e conexões |
| Arquivos       | Leitura e escrita    |

---

# 🌐 Testando aplicações HTTP

Outro recurso importante é o pacote:

```go
httptest
```

Esse pacote permite testar aplicações HTTP sem iniciar um servidor real.

---

## 💡 Benefícios do httptest

* ✅ Testes mais rápidos
* ✅ Maior isolamento
* ✅ Menor consumo de recursos
* ✅ Facilidade para validar rotas e respostas HTTP

---

# ⚠️ Cuidados importantes

> ⚠️ Testes mal organizados podem dificultar a manutenção do projeto.

> 🚨 Evite depender de serviços externos reais durante os testes automatizados.

> 💡 Quanto maior a cobertura de testes, maior a segurança durante alterações e refatorações.

---

# 🎯 Benefícios dos testes automatizados

* ✅ Redução de bugs
* ✅ Maior confiabilidade
* ✅ Facilidade de manutenção
* ✅ Segurança durante refatorações
* ✅ Melhor qualidade do software

---

# 📊 Resumo rápido

| Recurso      | Função              |
| ------------ | ------------------- |
| `testing`    | Framework de testes |
| `_test.go`   | Arquivos de teste   |
| `go test`    | Executa testes      |
| `go test -v` | Exibe detalhes      |
| `httptest`   | Testes HTTP         |

---

# ✅ Conclusão

Os testes automatizados são fundamentais para o desenvolvimento moderno em Go.

Eles ajudam a garantir estabilidade, qualidade e segurança no código, tornando as aplicações mais confiáveis e fáceis de evoluir ao longo do tempo.
