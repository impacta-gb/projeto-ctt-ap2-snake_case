Condicionais

Controlam o fluxo do programa com base em condições. 'if' é usado para lógica básica, 'if-else' para decisões binárias e 'switch' para múltiplas condições. O 'if' suporta inicialização opcional e não exige parênteses, mas requer chaves. O 'switch' suporta expressões, type switches e 'fallthrough'. São fundamentais para a lógica de negócios.

'if'

Estrutura condicional básica utilizada para executar código com base em condições booleanas. Suporta uma instrução de inicialização opcional antes da verificação da condição. Não exige parênteses ao redor da condição, mas as chaves são obrigatórias. Pode ser combinado com 'else if' para múltiplas condições. É a base do controle de fluxo.

'if-else'

Estrutura condicional usada para tomadas de decisão binárias. O 'if' testa uma condição, enquanto o 'else' executa um caminho alternativo. Pode incluir uma instrução de inicialização opcional. Não requer parênteses ao redor da condição, mas exige chaves. É fundamental para o controle de fluxo do programa.

'switch'

Forma mais limpa de comparar uma variável com múltiplos valores e executar blocos de código correspondentes. Não necessita de 'break', pois não há fall-through por padrão. Funciona com qualquer tipo comparável, suporta múltiplos valores por caso, expression switches e type switches. Geralmente é mais legível do que longas cadeias de 'if-else'.

Loops

Go possui apenas uma estrutura de repetição: o flexível 'for'. Sua forma básica contém inicialização, condição e pós-instrução. Também suporta 'for range' para arrays, slices, maps, strings e channels. Pode ser usado para criar loops infinitos ou no estilo 'while'. O fluxo pode ser controlado com 'break' e 'continue'.

'for-range'

Forma especial do loop 'for' usada para percorrer arrays, slices, maps, strings e channels. Retorna índice/chave e valor. Em strings, retorna o índice do rune e o valor do rune. Em channels, retorna apenas os valores. O identificador em branco '_' pode ser usado para ignorar valores retornados que não serão utilizados.