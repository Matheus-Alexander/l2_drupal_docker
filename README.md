# Avaliação Técnica - L2
Repositório criado para avaliação técnica da L2.
https://docs.google.com/document/d/1suu_15cHw0Dnr-mC3DUnr8kO78iXNH7hGHRyNyT5G24/edit?tab=t.0

## Requerimentos
- Docker
- Docker Compose
- Composer

## Instalação
 1. Clone o repositório para sua máquina local.
 2. Entre na pasta raíz do repositório.
 3. Rode o comando "make up".

## Cases

Os cases foram implementados como um custom content type.

### Criação
Para criar novos cases, navegue até http://drupal.docker.localhost:8000/node/add/case ou:

 1. Clique em "Conteúdo" no menu administrativo.
 2. Clique em "+Adicionar Conteúdo"
 3. Clique em "Case".
 4. Preencha os campos relevantes e clique em "Salvar".

### Visualização
Para ver os cases já criados, navegue até http://drupal.docker.localhost:8000/cases-l2 ou clique em "Cases L2" no menu de navegação.

A visualização dos cases foi feita utilizando a view cases_l2, acessível em http://drupal.docker.localhost:8000/admin/structure/views/view/cases_l2.

A estilização dos cards na página foi feita utilizando um custom theme Bootstrap5, fields de conteúdo ocultos e um texto personalizado com padrões de substituição para o resgae das informações de cada Case.
A paginação acontece à partir de 10 itens.
A página está sendo cached através de um timer de 1h. 

## REST API

A REST API foi criada utilizando o `drupal/rest_export` na view mencionada acima.
Os filtros foram criados através de critérios de filtragem expostos para o REST resource.
A REST API também tem um cache configurado na view timer-based de 1h.

Acesse o Swagger da REST API: https://matheus-alexander.github.io/l2_drupal_docker.

## Drupal
O repositório foi criado utilizando Docker4Drupal.
O banco de dados contendo a instalação Drupal está sendo carregado no compose do serviço mariadb através da pasta ./mariadb-init.
