A linguagem Go possui suporte nativo para testes automatizados através do pacote testing. Os testes são fundamentais para garantir que o código continue funcionando corretamente mesmo após modificações, ajudando na identificação de erros e aumentando a confiabilidade do sistema.
Os arquivos de teste em Go devem possuir o sufixo _test.go. Dentro desses arquivos, as funções de teste devem começar com a palavra Test. Por exemplo:
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
Para executar os testes do projeto, utiliza-se o comando:
go test
Caso seja necessário visualizar informações mais detalhadas da execução, é possível utilizar:
go test -v
Uma prática muito comum em Go é a utilização de testes guiados por tabela, conhecidos como table-driven tests. Essa técnica permite testar vários cenários de forma organizada e reduz a repetição de código.
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
Além disso, Go também permite o uso de mocks e stubs para simular dependências externas, como APIs e bancos de dados, tornando os testes mais rápidos e isolados. Outro recurso importante é o pacote httptest, utilizado para testar aplicações HTTP sem a necessidade de iniciar um servidor real.
Os testes automatizados ajudam a reduzir bugs, facilitam a manutenção do código e oferecem maior segurança durante alterações e refatorações no projeto.
