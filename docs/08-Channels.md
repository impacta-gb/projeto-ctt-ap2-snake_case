Channels são o principal mecanismo de comunicação entre goroutines em Go. Eles permitem enviar e receber dados entre tarefas concorrentes de forma segura, seguindo o princípio de “compartilhar memória através da comunicação”.
Os channels são tipados e criados utilizando a função make():
canal := make(chan int)
Exemplo de envio e recebimento de dados:
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
No exemplo acima:
canal <- valor envia dados
<-canal recebe dados
Os channels podem ser classificados em dois tipos:
Tipo
Característica
Sem buffer
Espera envio e recebimento simultâneo
Com buffer
Permite armazenar valores temporariamente

Exemplo de channel com buffer:
canal := make(chan int, 2)
Channels são utilizados para:
Sincronização entre goroutines
Comunicação segura de dados
Coordenação de tarefas concorrentes
Controle de execução
!!! note
 Channels ajudam a evitar problemas comuns de concorrência, como condições de corrida (race conditions).
Também é possível utilizar o comando close() para fechar um channel quando ele não será mais utilizado:
close(canal)
A combinação de goroutines e channels torna Go uma linguagem extremamente poderosa para desenvolvimento concorrente, permitindo criar aplicações eficientes, escaláveis e com código mais simples de manter.

