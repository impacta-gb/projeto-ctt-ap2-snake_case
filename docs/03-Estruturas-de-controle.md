# 🔀 Estruturas de Controle em Go

> Controlando decisões, condições e repetições em aplicações desenvolvidas com Go.

---

# 📌 O que são estruturas de controle?

As estruturas de controle permitem alterar o fluxo de execução do programa com base em:

* ✅ condições
* ✅ decisões
* ✅ repetições
* ✅ comparações

Em Go, os principais mecanismos são:

| Estrutura   | Função              |
| ----------- | ------------------- |
| `if`        | Executa condições   |
| `if-else`   | Tomadas de decisão  |
| `switch`    | Múltiplas condições |
| `for`       | Repetições          |
| `for-range` | Percorrer coleções  |

---

# 🔍 Condicionais

As estruturas condicionais controlam o fluxo do programa com base em expressões booleanas.

---

# ⚙️ if

A estrutura `if` é utilizada para executar código apenas quando uma condição for verdadeira.

---

## 💻 Exemplo simples

```go id="h4mb9x"
idade := 18

if idade >= 18 {
    fmt.Println("Maior de idade")
}
```

---

# 🚀 Características do if

| Característica         | Descrição               |
| ---------------------- | ----------------------- |
| Sem parênteses         | Go não exige `()`       |
| Chaves obrigatórias    | `{}` são obrigatórias   |
| Inicialização opcional | Permite criar variáveis |

---

## 💻 if com inicialização

```go id="jlwmv7"
if valor := 10; valor > 5 {
    fmt.Println("Valor maior que 5")
}
```

> 💡 A variável criada no `if` existe apenas dentro do bloco condicional.

---

# ⚖️ if-else

A estrutura `if-else` permite criar decisões binárias.

---

## 💻 Exemplo

```go id="l9tvf0"
numero := 7

if numero % 2 == 0 {
    fmt.Println("Número par")
} else {
    fmt.Println("Número ímpar")
}
```

---

# 🔄 else if

Também é possível trabalhar com múltiplas condições.

## 💻 Exemplo

```go id="d4owj8"
nota := 8

if nota >= 9 {
    fmt.Println("Excelente")
} else if nota >= 7 {
    fmt.Println("Aprovado")
} else {
    fmt.Println("Reprovado")
}
```

---

# 🧠 switch

O `switch` é uma forma mais limpa de comparar múltiplos valores.

Diferente de outras linguagens:

* ✅ não exige `break`
* ✅ não possui fall-through automático
* ✅ melhora legibilidade

---

## 💻 Exemplo simples

```go id="ny5zra"
dia := 2

switch dia {
case 1:
    fmt.Println("Domingo")

case 2:
    fmt.Println("Segunda-feira")

default:
    fmt.Println("Outro dia")
}
```

---

# 🚀 Recursos do switch

| Recurso           | Função                       |
| ----------------- | ---------------------------- |
| Expression switch | Comparação de expressões     |
| Type switch       | Verificação de tipos         |
| Múltiplos valores | Vários casos no mesmo bloco  |
| `fallthrough`     | Continua para o próximo case |

---

## 💻 Exemplo com múltiplos valores

```go id="f0g32g"
switch letra {
case "a", "e", "i", "o", "u":
    fmt.Println("Vogal")
}
```

---

# 🔁 Loops em Go

Go possui apenas uma estrutura de repetição:

```text id="mo7b9k"
for
```

Apesar disso, ela é extremamente flexível.

---

# 💻 Loop tradicional

```go id="azcqfe"
for i := 0; i < 5; i++ {
    fmt.Println(i)
}
```

---

# ⚙️ Estrutura do for

| Parte         | Função             |
| ------------- | ------------------ |
| Inicialização | Define variável    |
| Condição      | Controla repetição |
| Pós-instrução | Atualiza valor     |

---

# ♾️ Loop infinito

Também é possível criar loops infinitos.

## 💻 Exemplo

```go id="wckr3u"
for {
    fmt.Println("Executando...")
}
```

---

# 🔄 for-range

O `for-range` é utilizado para percorrer:

* ✅ arrays
* ✅ slices
* ✅ maps
* ✅ strings
* ✅ channels

---

# 💻 Exemplo com slice

```go id="m1o5h5"
nomes := []string{"Ana", "Carlos", "Maria"}

for indice, valor := range nomes {
    fmt.Println(indice, valor)
}
```

---

# 📦 Valores retornados

O `for-range` normalmente retorna:

| Estrutura     | Retorno        |
| ------------- | -------------- |
| Arrays/Slices | Índice e valor |
| Maps          | Chave e valor  |
| Strings       | Índice e rune  |
| Channels      | Apenas valores |

---

# ⚡ Ignorando valores

O identificador `_` pode ser utilizado para ignorar valores retornados.

## 💻 Exemplo

```go id="1a3j1v"
for _, valor := range nomes {
    fmt.Println(valor)
}
```

> 💡 O `_` é conhecido como identificador em branco.

---

# 🛑 break e continue

O fluxo do loop pode ser controlado utilizando:

| Comando    | Função                      |
| ---------- | --------------------------- |
| `break`    | Interrompe o loop           |
| `continue` | Pula para próxima repetição |

---

## 💻 Exemplo com continue

```go id="rj7p63"
for i := 0; i < 5; i++ {

    if i == 2 {
        continue
    }

    fmt.Println(i)
}
```

---

# ⚠️ Cuidados importantes

> ⚠️ Loops infinitos podem consumir muitos recursos se não forem controlados corretamente.

> 🚨 Uso excessivo de condicionais aninhadas pode dificultar a leitura do código.

> 💡 Prefira utilizar `switch` quando houver muitas comparações da mesma variável.

---

# 🎯 Benefícios das estruturas de controle

* ✅ Controle do fluxo da aplicação
* ✅ Maior organização
* ✅ Código mais legível
* ✅ Melhor manutenção
* ✅ Flexibilidade lógica

---

# 📊 Resumo rápido

| Estrutura   | Objetivo                   |
| ----------- | -------------------------- |
| `if`        | Executar condições         |
| `if-else`   | Tomar decisões             |
| `switch`    | Comparar múltiplos valores |
| `for`       | Criar repetições           |
| `for-range` | Percorrer coleções         |

---

# ✅ Conclusão

As estruturas de controle são fundamentais para qualquer aplicação desenvolvida em Go.

Elas permitem controlar decisões, repetições e fluxos lógicos de maneira simples, eficiente e organizada.
