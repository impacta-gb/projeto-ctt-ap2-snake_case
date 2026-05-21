Goroutines são threads leves gerenciadas pelo runtime da linguagem Go que permitem a execução concorrente de funções. Elas são uma das funcionalidades mais poderosas da linguagem, tornando simples a criação de programas concorrentes e paralelos.
Uma goroutine é criada utilizando a palavra-chave go antes da chamada de uma função:
go minhaFuncao()
Exemplo completo:
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
As goroutines possuem baixo consumo de memória e podem ser criadas em grande quantidade, permitindo que milhares ou até milhões delas executem simultaneamente. O runtime do Go é responsável pelo gerenciamento e escalonamento automático entre os núcleos da CPU.
!!! tip
 Goroutines são ideais para tarefas concorrentes como processamento paralelo, servidores web e operações de rede.
Diferente das threads tradicionais dos sistemas operacionais, as goroutines são mais leves e eficientes, pois o próprio runtime da linguagem controla sua execução.
As goroutines normalmente se comunicam através de channels, seguindo o princípio de “não compartilhe memória diretamente; compartilhe memória através da comunicação”.
!!! warning
 Criar muitas goroutines sem controle pode causar consumo excessivo de recursos e dificultar a sincronização das tarefas.
A concorrência em Go facilita o desenvolvimento de aplicações modernas e escaláveis, especialmente em sistemas distribuídos, APIs e aplicações de alto desempenho.
