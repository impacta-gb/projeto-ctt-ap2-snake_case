# 📦 Go Modules

> Gerenciamento moderno de dependências e versões em projetos desenvolvidos com Go.

---

## 📌 O que são Go Modules?

O gerenciamento de dependências em Go é realizado através do sistema chamado **Go Modules**.

Ele é o padrão oficial da linguagem para:

* ✅ controlar versões de bibliotecas
* ✅ organizar dependências
* ✅ garantir builds reproduzíveis
* ✅ evitar conflitos entre ambientes

Os Go Modules tornam o desenvolvimento mais organizado, confiável e escalável.

---

# 🚀 Inicializando um projeto Go

Ao iniciar um projeto Go, é criado um arquivo chamado `go.mod`.

Esse arquivo é responsável por armazenar:

| Informação     | Função                       |
| -------------- | ---------------------------- |
| Nome do módulo | Identificação do projeto     |
| Versão do Go   | Compatibilidade da linguagem |
| Dependências   | Bibliotecas utilizadas       |

---

## 💻 Criando o arquivo `go.mod`

O comando abaixo inicializa um novo módulo Go:

```go
go mod init meu-projeto
```

> 💡 Esse comando prepara o ambiente para o gerenciamento automático de dependências.

---

# 📂 Estrutura do go.mod

Após executar o comando, o Go cria automaticamente o arquivo:

```text
go.mod
```

Exemplo simplificado:

```go
module meu-projeto

go 1.22
```

---

# 📥 Instalando dependências

Quando uma biblioteca externa é importada no projeto, o Go consegue baixá-la automaticamente.

## Exemplo

```go
import "github.com/gin-gonic/gin"
```

> 🚀 O Go identifica a dependência e realiza o download automaticamente.

---

# 🧹 Organizando dependências

Um dos comandos mais importantes é o:

```go
go mod tidy
```

Esse comando é utilizado para:

* ✅ adicionar dependências faltantes
* ✅ remover bibliotecas não utilizadas
* ✅ manter o projeto limpo
* ✅ evitar arquivos desnecessários

---

## 💡 Boa prática

> Execute `go mod tidy` frequentemente para manter o projeto organizado e evitar dependências inúteis.

---

# 📦 Pasta vendor

Outro comando importante é:

```go
go mod vendor
```

Esse comando cria uma pasta chamada:

```text
vendor/
```

contendo cópias locais de todas as dependências utilizadas pelo projeto.

---

# 🛠️ Quando usar vendor?

A pasta `vendor/` pode ser útil em situações como:

| Situação               | Benefício                             |
| ---------------------- | ------------------------------------- |
| Builds offline         | Dependências locais                   |
| Ambientes corporativos | Maior controle                        |
| Segurança              | Evita alterações externas inesperadas |
| Reprodutibilidade      | Builds consistentes                   |

---

# ⚠️ Cuidados importantes

> ⚠️ Dependências desatualizadas podem causar falhas de compatibilidade no projeto.

> 🚨 Evite adicionar bibliotecas desnecessárias para não aumentar a complexidade da aplicação.

> 💡 Utilize apenas dependências confiáveis e bem mantidas pela comunidade.

---

# 🎯 Benefícios dos Go Modules

* ✅ Controle de versões
* ✅ Melhor organização
* ✅ Builds reproduzíveis
* ✅ Facilidade de manutenção
* ✅ Compatibilidade entre ambientes

---

# 📊 Resumo rápido

| Recurso         | Função                   |
| --------------- | ------------------------ |
| `go.mod`        | Gerencia dependências    |
| `go mod init`   | Inicializa o módulo      |
| `go mod tidy`   | Limpa dependências       |
| `go mod vendor` | Cria dependências locais |

---

# ✅ Conclusão

Os Go Modules são essenciais para qualquer projeto moderno desenvolvido em Go.

Eles simplificam o gerenciamento de dependências, aumentam a confiabilidade do projeto e tornam o desenvolvimento mais organizado e previsível.
