Integrantes do Grupo

Andressa Ayumi Kitajima - 2501165
Lucas Lucio de Paiva - 2500458
Lucas Rodrigues Melo - 2500289
Maria Luiza Moreira de Alcântara - 2501392

Fluxo de Trabalho da Equipe

O desenvolvimento do projeto foi realizado utilizando um fluxo colaborativo baseado em Feature Branches, Pull Requests e Code Reviews no GitHub.

A branch main foi protegida utilizando as Branch Protection Rules, impedindo commits diretos e garantindo que todas as alterações passassem obrigatoriamente por revisão antes do merge.

Para cada nova funcionalidade, página de documentação ou alteração no workflow, era criada uma branch separada.

Após finalizar a implementação, o integrante responsável abria um Pull Request para a branch main. Outro membro da equipe realizava a revisão do código.

Arquitetura do Workflow GitHub Actions

O projeto utiliza GitHub Actions para automatizar os processos de validação, build e deploy da documentação criada no Zensical. O workflow foi dividido em dois jobs principais: build_site e deploy_site.

O job build_site é responsável por configurar o ambiente Python, instalar as dependências e gerar os arquivos HTML da documentação. Também foi utilizada uma Matrix Strategy para testar o projeto nas versões 3.10 e 3.11 do Python, garantindo compatibilidade em diferentes ambientes.

Para melhorar o desempenho do pipeline, foi implementado cache das dependências com actions/cache, reduzindo o tempo de execução do workflow.

Após o build, os arquivos gerados são enviados como artefatos utilizando actions/upload-artifact. O job deploy_site, que depende da conclusão do build através da diretiva needs, faz o download desses arquivos e publica automaticamente o site no GitHub Pages.

Por segurança, o deploy não é executado durante Pull Requests, ocorrendo apenas em pushes na branch main e em execuções agendadas com schedule.

O workflow foi configurado para rodar automaticamente em Pull Requests, pushes na branch principal e execuções semanais, garantindo validação contínua e publicação automatizada da documentação.