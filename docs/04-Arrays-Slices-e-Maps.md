# 📚 Arrays, Slices e Maps em Go

> Estruturas fundamentais para armazenamento, manipulação e organização de dados em aplicações Go.

---

# 📌 Arrays

Arrays são sequências de tamanho fixo compostas por elementos do mesmo tipo.

Em Go, o tamanho do array faz parte do tipo. Isso significa que arrays com tamanhos diferentes são considerados tipos diferentes.

---

## 💻 Exemplo de Array

```go id="l4eqrc"
var numeros [5]int
```

Nesse exemplo:

* o array possui tamanho fixo de `5`
* todos os elementos são do tipo `int`

---

# ⚙️ Características dos Arrays

| Característica           | Descrição                               |
| ------------------------ | --------------------------------------- |
| Tamanho fixo             | Não pode ser alterado                   |
| Tipo homogêneo           | Todos os elementos possuem o mesmo tipo |
| Tipo por valor           | O array é copiado ao ser atribuído      |
| Inicialização automática | Valores zero são atribuídos             |

---

# ⚠️ Arrays em Go

Arrays são tipos por valor.

Isso significa que:

* ao atribuir um array para outro,
* ou ao passá-lo para funções,

o conteúdo inteiro será copiado.

> 💡 Apesar de importantes, arrays são menos utilizados no dia a dia devido à flexibilidade dos slices.

---

# 🔄 Slices

Slices são arrays dinâmicos construídos sobre arrays.

Eles representam o tipo de sequência mais utilizado em Go.

---

## 🚀 Principais vantagens dos Slices

* ✅ tamanho dinâmico
* ✅ maior flexibilidade
* ✅ melhor reutilização
* ✅ operações práticas
* ✅ baixo custo de uso

---

# 💻 Criando um Slice

## Utilizando make()

```go id="by0qho"
slice := make([]int, 5)
```

---

## Utilizando literal

```go id="ls2g6h"
slice := []int{1, 2, 3}
```

---

# 📦 Comprimento e Capacidade

Slices possuem:

| Propriedade | Função                  |
| ----------- | ----------------------- |
| Length      | Quantidade de elementos |
| Capacity    | Espaço total disponível |

---

# 📈 Crescimento de Slices

Durante operações de `append`, o Go pode aumentar automaticamente a capacidade do slice.

Normalmente:

* slices pequenos dobram de tamanho
* novos arrays podem ser realocados automaticamente

---

## 💻 Exemplo com append

```go id="9w8y3r"
slice = append(slice, 10)
```

> 🚀 O `append()` adiciona novos elementos dinamicamente ao slice.

---

# ⚡ Pré-alocação de memória

É possível otimizar memória utilizando:

```go id="vuy1lp"
make([]int, 5, 10)
```

Nesse exemplo:

| Valor | Função                    |
| ----- | ------------------------- |
| `5`   | Comprimento inicial       |
| `10`  | Capacidade máxima inicial |

> 💡 Pré-alocar capacidade reduz realocações e melhora desempenho.

---

# 🛠️ A função make()

A função `make()` é utilizada para criar e inicializar:

* ✅ slices
* ✅ maps
* ✅ channels

---

## 💻 Exemplos

```go id="lk0r8m"
make([]int, 5, 10)
make(map[string]int)
make(chan int)
```

---

# ⚖️ make() vs new()

| Função   | Característica                      |
| -------- | ----------------------------------- |
| `make()` | Retorna estruturas prontas para uso |
| `new()`  | Retorna ponteiros                   |

> 💡 `make()` é essencial para inicializar tipos por referência.

---

# 🔄 Conversão de Slice para Array

A partir do Go 1.17+, é possível converter slices em arrays.

## 💻 Exemplo

```go id="p3ekhh"
array := [3]int(slice)
```

---

# ⚠️ Cuidados na conversão

> ⚠️ O programa gera panic caso o slice possua menos elementos que o tamanho do array.

Essa conversão é útil quando são necessárias:

* garantias de tamanho
* semântica de array
* validações mais rígidas

---

# 🔁 Conversão de Array para Slice

Arrays podem ser convertidos em slices utilizando:

```go id="i6rxhc"
array[:]
array[start:end]
```

---

## 💻 Exemplo

```go id="f3x7tm"
slice := array[1:3]
```

> 💡 O slice criado compartilha a mesma memória do array original.

---

# ⚠️ Compartilhamento de memória

Alterações feitas pelo slice afetam diretamente o array original.

Isso ocorre porque:

* slices apontam para os dados do array
* não há cópia automática dos elementos

---

# 🗺️ Maps

Maps são tipos associativos embutidos que relacionam:

> chave → valor

São amplamente utilizados para buscas rápidas e armazenamento estruturado de dados.

---

# 💻 Criando um Map

## Utilizando make()

```go id="r8sk0l"
idades := make(map[string]int)
```

---

## Utilizando literal

```go id="wjqzn0"
idades := map[string]int{
    "Ana": 20,
    "Carlos": 30,
}
```

---

# 🚀 Operações com Maps

| Operação    | Função             |
| ----------- | ------------------ |
| Inserção    | Adiciona elementos |
| Busca       | Recupera valores   |
| Remoção     | Exclui elementos   |
| Atualização | Modifica valores   |

---

# 🔍 Verificando existência de chave

Go utiliza o padrão:

```go id="exi7gf"
valor, ok := mapa[chave]
```

---

## 💻 Exemplo

```go id="90g9zq"
idade, ok := idades["Ana"]
```

| Valor   | Significado              |
| ------- | ------------------------ |
| `idade` | Valor encontrado         |
| `ok`    | Indica se a chave existe |

---

# ⚠️ Cuidados importantes

> ⚠️ Arrays possuem tamanho fixo e pouca flexibilidade.

> 🚨 Alterações em slices podem afetar o array original.

> 💡 Utilize slices para maior flexibilidade e arrays quando tamanho fixo for necessário.

---

# 🎯 Benefícios dessas estruturas

* ✅ Organização de dados
* ✅ Melhor desempenho
* ✅ Flexibilidade
* ✅ Facilidade de manipulação
* ✅ Estruturas eficientes

---

# 📊 Resumo rápido

| Estrutura | Característica              |
| --------- | --------------------------- |
| Array     | Tamanho fixo                |
| Slice     | Estrutura dinâmica          |
| Map       | Associação chave-valor      |
| make()    | Inicialização de estruturas |

---

# ✅ Conclusão

Arrays, slices e maps são estruturas fundamentais na linguagem Go.

Eles permitem criar aplicações mais organizadas, eficientes e flexíveis, sendo amplamente utilizados em praticamente qualquer projeto desenvolvido com a linguagem.
