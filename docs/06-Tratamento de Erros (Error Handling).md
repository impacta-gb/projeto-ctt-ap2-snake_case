Go utiliza um sistema de tratamento de erros explícito baseado em valores de retorno do tipo error. Diferente de outras linguagens que utilizam exceções automáticas, em Go os erros devem ser verificados manualmente pelo programador, tornando o fluxo do programa mais previsível e fácil de entender.
Normalmente, as funções retornam o erro como o último valor de retorno. O padrão mais utilizado para verificar falhas é:
if err != nil {
   // tratamento do erro
}
Exemplo:
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
Para criar erros personalizados, Go oferece a função errors.New():
err := errors.New("erro personalizado")
Também é possível utilizar fmt.Errorf() para criar mensagens formatadas:
err := fmt.Errorf("falha ao conectar no servidor")
!!! warning
 Ignorar erros pode causar comportamentos inesperados e dificultar a manutenção do sistema.
Outra característica importante é que Go não possui tratamento tradicional de exceções (try/catch). Em vez disso, os erros são considerados valores comuns que devem ser tratados explicitamente. Essa abordagem incentiva boas práticas e aumenta a confiabilidade do código.
Além disso, Go possui os mecanismos panic e recover, utilizados em situações críticas. O panic interrompe a execução normal do programa, enquanto recover pode capturar esse erro e evitar que a aplicação seja encerrada completamente.
Exemplo:
panic("erro crítico")
O tratamento de erros é uma das características mais importantes da linguagem Go, contribuindo para a criação de aplicações robustas, seguras e fáceis de manter.
