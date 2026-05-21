Arrays

Arrays são sequências de tamanho fixo compostas por elementos do mesmo tipo. O tamanho faz parte do tipo, então arrays com tamanhos diferentes são considerados tipos diferentes. São declarados com um comprimento específico e inicializados com valores zero. Arrays são tipos por valor, ou seja, são copiados ao serem atribuídos ou passados para funções. Apesar disso, slices são mais utilizados devido à maior flexibilidade. Arrays são importantes para entender o sistema de tipos do Go.

Slices

Slices são arrays dinâmicos construídos sobre arrays. São tipos por referência que possuem comprimento e capacidade. Podem ser criados com 'make()' ou com literais de slice. Suportam operações como 'append' e 'copy'. São muito mais flexíveis que arrays e representam o tipo de sequência mais utilizado em Go.

Capacidade e Crescimento

A capacidade de um slice determina quando ocorrerá uma realocação durante operações de 'append'. O Go normalmente dobra a capacidade para slices menores. É possível pré-alocar memória usando 'make([]T, length, capacity)' para otimizar o uso de memória e reduzir alocações em códigos críticos de desempenho.

'make()'

Função utilizada para criar e inicializar slices, maps e channels. Diferente de 'new()', ela retorna valores prontos para uso. Exemplos: 'make([]int, 5, 10)' para slices, 'make(map[string]int)' para maps e 'make(chan int)' para channels. É essencial para inicializar tipos por referência.

Conversão de Slice para Array

É possível converter um slice em array usando '[N]T(slice)' (Go 1.17+). A conversão copia os dados do slice para um array de tamanho fixo. O programa gera panic caso o slice possua menos de N elementos. É útil quando são necessárias garantias de tamanho específico ou semântica de array.

Conversão de Array para Slice

Arrays podem ser convertidos em slices usando expressões como 'array[:]' ou 'array[start:end]'. Isso cria um cabeçalho de slice apontando para a memória do array sem copiar os dados. Alterações feitas pelo slice afetam o array original. É uma forma eficiente de utilizar arrays com APIs baseadas em slices.

Maps

Maps são tipos associativos embutidos que relacionam chaves a valores. São tipos por referência criados com 'make(map[KeyType]ValueType)' ou com literais de map. As chaves precisam ser tipos comparáveis. Suportam operações de inserção, remoção e busca. A existência de uma chave pode ser verificada usando o padrão 'value, ok := map[key]'.