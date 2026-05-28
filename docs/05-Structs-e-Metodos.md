# 🧩 Structs e Methods em Go

> Organizando dados e comportamentos utilizando composição e programação orientada a objetos em Go.

---

## 📌 O que são Structs?

Structs são tipos de dados personalizados que agrupam campos relacionados sob um único nome.

Elas permitem:

* ✅ criar modelos de dados complexos
* ✅ organizar informações
* ✅ estruturar aplicações
* ✅ representar entidades do sistema

Embora sejam semelhantes a classes, em Go os métodos são definidos separadamente.

---

# 💻 Exemplo de Struct

```go id="yhkf2u"
type Usuario struct {
    Nome  string
    Idade int
}
```

---

# 🔍 Acessando campos

Os campos de uma struct são acessados utilizando a notação com ponto.

## Exemplo

```go id="f2mlrt"
usuario.Nome
usuario.Idade
```

> 💡 Structs podem ser passadas para funções, retornadas e utilizadas em qualquer parte da aplicação.

---

# 📦 Benefícios das Structs

| Recurso        | Benefício                        |
| -------------- | -------------------------------- |
| Organização    | Agrupa dados relacionados        |
| Reutilização   | Facilita reutilização de modelos |
| Clareza        | Código mais limpo                |
| Escalabilidade | Estrutura aplicações complexas   |

---

# 🏷️ Struct Tags e JSON

Struct tags fornecem metadados sobre os campos utilizando crases com pares chave-valor.

As tags JSON são muito utilizadas para:

* ✅ APIs
* ✅ serialização de dados
* ✅ integração com frontend
* ✅ comunicação entre sistemas

---

## 💻 Exemplo de Struct Tags

```go id="7jccm7"
type Usuario struct {
    Nome string `json:"nome"`
    Email string `json:"email,omitempty"`
}
```

---

# 📚 Principais tags JSON

| Tag           | Função                 |
| ------------- | ---------------------- |
| `json:"nome"` | Define o nome do campo |
| `omitempty`   | Omite campos vazios    |
| `-`           | Ignora o campo         |

---

# 🔄 Embedding de Structs

O embedding permite incluir uma struct dentro de outra sem utilizar nomes de campos.

Isso torna os campos embutidos diretamente acessíveis.

---

## 💻 Exemplo de Embedding

```go id="u7h0gc"
type Endereco struct {
    Cidade string
}

type Usuario struct {
    Nome string
    Endereco
}
```

---

# 🚀 Vantagens do Embedding

| Benefício     | Descrição              |
| ------------- | ---------------------- |
| Reutilização  | Compartilha estruturas |
| Flexibilidade | Facilita composição    |
| Simplicidade  | Evita repetições       |
| Organização   | Código mais limpo      |

---

# ⚖️ Composição vs Herança

Go prioriza:

> **Composição em vez de herança**

Essa abordagem torna o código:

* ✅ mais flexível
* ✅ mais reutilizável
* ✅ mais simples de manter

---

# ⚙️ Methods em Go

Methods são funções associadas a tipos específicos, normalmente structs.

Eles permitem que objetos tenham comportamentos próprios.

---

## 💻 Exemplo de Method

```go id="78r5gl"
type Usuario struct {
    Nome string
}

func (u Usuario) Saudacao() {
    fmt.Println("Olá,", u.Nome)
}
```

---

# 📌 O que é um Receiver?

O receiver é o valor definido antes do nome da função.

```go id="y2pr15"
func (u Usuario) Saudacao()
```

Nesse exemplo:

| Elemento   | Função         |
| ---------- | -------------- |
| `u`        | Receiver       |
| `Usuario`  | Tipo associado |
| `Saudacao` | Method         |

---

# 🔄 Receiver por valor vs ponteiro

Methods podem utilizar:

| Tipo                  | Característica             |
| --------------------- | -------------------------- |
| Receiver por valor    | Não altera dados originais |
| Receiver por ponteiro | Permite modificar dados    |

---

## 💻 Exemplo com ponteiro

```go id="jw4f60"
func (u *Usuario) AtualizarNome(nome string) {
    u.Nome = nome
}
```

> 💡 Receivers por ponteiro são recomendados quando o método precisa modificar os dados da struct.

---

# ⚠️ Cuidados importantes

> ⚠️ Structs muito grandes podem dificultar a manutenção do sistema.

> 🚨 Uso excessivo de embedding pode tornar o código confuso.

> 💡 Prefira composição simples e reutilizável.

---

# 🎯 Benefícios de Structs e Methods

* ✅ Organização do código
* ✅ Encapsulamento de lógica
* ✅ Reutilização de componentes
* ✅ Facilidade de manutenção
* ✅ Programação orientada a objetos

---

# 📊 Resumo rápido

| Recurso     | Objetivo               |
| ----------- | ---------------------- |
| Struct      | Agrupar dados          |
| Method      | Definir comportamentos |
| Struct Tags | Metadados              |
| Embedding   | Reutilização           |
| Receiver    | Associação de métodos  |

---

# ✅ Conclusão

Structs e Methods são fundamentais para o desenvolvimento de aplicações modernas em Go.

Eles permitem organizar dados, encapsular comportamentos e criar sistemas mais estruturados, reutilizáveis e fáceis de manter.
