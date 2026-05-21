##Hello World em Go

O tradicional primeiro programa demonstra a estrutura básica: 'package main', importação do 'fmt' e a função 'main()' usando 'fmt.Println()'. Ensina a sintaxe do Go, compilação, execução e verifica se o ambiente de desenvolvimento está configurado corretamente. É o ponto de entrada para aprender Go.

##Comando go

Ferramenta principal para gerenciar o código-fonte da Go, oferecendo uma interface unificada para compilar, testar, formatar código e gerenciar dependências. Inclui subcomandos como 'build', 'run', 'test', 'fmt' e 'mod'. Automatiza todo o fluxo de desenvolvimento.

##Variáveis e Constantes

Variáveis armazenam valores que podem ser alterados, sendo declaradas com 'var' ou ':='. Constantes armazenam valores imutáveis, declaradas com 'const'. As variáveis podem ter tipos definidos explicitamente ou utilizar inferência de tipo. Constantes precisam ser determinadas em tempo de compilação. Ambos suportam declarações em bloco e escopo de pacote ou função.

##Valores Zero

São os valores padrão atribuídos a variáveis não inicializadas: '0' para números, 'false' para booleanos, '""' para strings e 'nil' para pointers, slices e maps. Isso garante um estado inicial previsível e reduz erros de inicialização. É um conceito fundamental para criar código confiável em Go.

##const e iota

Constantes declaradas com const representam valores fixos em tempo de compilação. O iota cria constantes inteiras sequenciais começando em zero e reinicia a cada bloco const. É muito utilizado para enumerações, flags de bits e sequências de constantes sem a necessidade de definir valores manualmente.

##Escopo e Shadowing

Escopo determina onde uma variável pode ser acessada, variando do nível global até blocos internos. Shadowing ocorre quando uma variável em um escopo interno “esconde” outra variável com o mesmo nome em um escopo externo. Go possui escopo de pacote, função e bloco. Entender esse comportamento ajuda a evitar bugs causados pela criação acidental de novas variáveis.