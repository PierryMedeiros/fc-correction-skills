---
name: corrige-clean-architecture-go
description: >
  Corrige e avalia o desafio de Clean Architecture com Listagem de Orders em Go.
  TRIGGER quando: desafio de clean architecture, clean arch, listagem de orders,
  ListOrders, REST gRPC GraphQL, use case, caso de uso, arquitetura limpa,
  docker compose up, migracoes, orders, pedidos, api.http.
  Palavras-chave: clean architecture, clean arch, ListOrders, orders, pedidos,
  REST, gRPC, GraphQL, Go, docker compose, migracoes, use case, api.http,
  arquitetura limpa, Dockerfile, listagem.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Clean Architecture: Listagem de Orders em Go

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Clean Architecture: Listagem de Orders (REST, gRPC e GraphQL)".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Execute `docker compose up -d --build` no diretorio do projeto.
2. Aguarde os containers subirem (use `sleep 15` ou verifique com `docker compose ps`).
3. Teste REST: crie uma order com `curl -X POST` e liste com `curl` no endpoint GET /order (verifique a porta no docker-compose ou codigo).
4. Teste GraphQL: envie query de listagem via `curl -X POST` no endpoint GraphQL.
5. Teste gRPC: invoque o metodo `ListOrders` via `grpcurl`. Como `grpcurl` pode nao estar instalado localmente, use a imagem `fullstorydev/grpcurl` com `docker run --rm --network host fullstorydev/grpcurl -plaintext localhost:<porta> <pacote>.<Service>/ListOrders` (ajuste host/porta conforme o docker-compose). A flag `--rm` e OBRIGATORIA para o container ser removido automaticamente apos a execucao e nao acumular lixo. Se o servico nao tiver reflection habilitado, use `-proto` apontando para o `.proto` montado via `-v`.
6. Ao final, execute `docker compose down -v` para limpar. Confirme tambem com `docker ps -a` que nao sobrou nenhum container `fullstorydev/grpcurl` (nao deve sobrar se `--rm` foi usado); se sobrar, remova com `docker rm -f`.
7. Inclua os resultados da execucao na sua avaliacao. Se o `docker compose up` falhar ou os endpoints (REST, gRPC ou GraphQL) nao responderem, inclua os erros no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `docker-compose.yml` ou `docker-compose.yaml`
- `Dockerfile` (para a aplicacao Go)
- Codigo-fonte da aplicacao em Go (ex: `main.go` ou estrutura de pastas como `cmd/`, `internal/`, etc)
- Arquivo `api.http` na raiz do projeto (com requisicoes prontas para criar e listar orders)
- `README.md`

### 2. Analise do Use Case ListOrders
Verifique se existe um caso de uso (Use Case) dedicado a listagem de pedidos:
- Deve existir um `ListOrdersUseCase` (ou equivalente) que encapsula a logica de listar todos os pedidos.
- O Use Case deve ser desacoplado das interfaces de entrada (REST, gRPC, GraphQL), seguindo os principios da Clean Architecture.
- Verifique se o Use Case interage com um repositorio/interface para buscar os dados do banco.

### 3. Analise da Interface REST
Verifique se o sistema expoe um endpoint REST para listar orders:
- **Endpoint:** `GET /order` (ou equivalente como `GET /orders`).
- O endpoint deve retornar a lista de orders em formato JSON.
- O servidor web deve estar configurado em uma porta (verificar no docker-compose ou no codigo).

### 4. Analise da Interface gRPC
Verifique se o sistema expoe um servico gRPC para listar orders:
- Deve existir um arquivo `.proto` definindo o servico com um metodo `ListOrders` (ou equivalente).
- O servico gRPC deve estar implementado em Go, chamando o Use Case.
- O servidor gRPC deve estar configurado em uma porta (verificar no docker-compose ou no codigo).

### 5. Analise da Interface GraphQL
Verifique se o sistema expoe uma query GraphQL para listar orders:
- Deve existir uma query `ListOrders` (ou equivalente como `listOrders`, `orders`, etc) no schema GraphQL.
- O resolver deve chamar o Use Case de listagem.
- O servidor GraphQL deve estar configurado em uma porta (verificar no docker-compose ou no codigo).

### 6. Analise do Banco de Dados e Migracoes
Verifique se:
- O banco de dados e provisionado via Docker (no docker-compose).
- Existem migracoes para criar as tabelas necessarias (ex: tabela `orders`).
- As migracoes devem ser aplicadas automaticamente ao executar `docker compose up`.

### 7. Analise do Docker/Docker Compose
Verifique se:
- Existe um `Dockerfile` para a aplicacao Go.
- O `docker-compose.yaml` sobe o banco de dados e o container da aplicacao.
- Ao rodar `docker compose up`, tudo deve funcionar automaticamente: banco sobe, migracoes sao aplicadas, aplicacao inicia.
- A aplicacao deve aguardar o banco estar pronto antes de iniciar (ex: `depends_on` com healthcheck, script de wait, ou similar).

### 8. Analise do Arquivo api.http
Verifique se existe um arquivo `api.http` na raiz contendo:
- Requisicao para **criar** uma Order (ex: `POST /order`).
- Requisicao para **listar** as Orders (ex: `GET /order`).

### 9. Analise do README.md
Verifique se o README contem:
- O comando unico de execucao (`docker compose up` ou similar).
- As portas em que cada servico (Web/REST, gRPC, GraphQL) esta rodando.

### 10. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (nao deve ser um monorepo com outros desafios).
- Todo o codigo deve estar na branch `main`.
- A arquitetura deve seguir os principios de Clean Architecture: separacao entre entidades, use cases, interfaces e infraestrutura.

### 11. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Todos os arquivos obrigatorios estao presentes (docker-compose, Dockerfile, api.http, README).
- Existe um Use Case de listagem de orders (ListOrdersUseCase ou equivalente).
- O sistema expoe a listagem de orders via **REST** (endpoint GET).
- O sistema expoe a listagem de orders via **gRPC** (servico com metodo ListOrders).
- O sistema expoe a listagem de orders via **GraphQL** (query de listagem).
- O banco de dados e provisionado via Docker.
- As migracoes sao aplicadas automaticamente com `docker compose up`.
- Existe um `Dockerfile` para a aplicacao.
- O `docker-compose.yaml` sobe banco e aplicacao.
- O arquivo `api.http` contem requisicoes para criar e listar orders.
- O README contem o comando de execucao e as portas dos servicos.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O Use Case de listagem de orders nao foi implementado' ou 'O sistema nao expoe a listagem via gRPC' ou 'As migracoes nao sao aplicadas automaticamente com docker compose up']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Implementar a funcionalidade de Listagem de Orders em uma aplicacao Clean Architecture em Go. O objetivo e provar o desacoplamento da arquitetura criando um unico Use Case (ListOrders) exposto atraves de tres interfaces de comunicacao diferentes simultaneamente.

Tecnologias: Go (Golang), Clean Architecture, REST, gRPC, GraphQL, Docker e Docker Compose.

Requisitos Tecnicos:
1. Use Case: Criar o caso de uso de listagem de pedidos (ListOrdersUseCase).
2. Interfaces de Entrada: Disponibilizar o acesso ao Use Case atraves de REST (GET /order), gRPC (Service ListOrders) e GraphQL (Query ListOrders).
3. Banco de Dados: Criar migracoes para as tabelas. Banco provisionado via Docker.
4. Dockerizacao: Container da aplicacao com Dockerfile. Docker Compose sobe banco e aplicacao. Tudo automatico com `docker compose up` (migracoes aplicadas, aplicacao disponivel).
5. api.http: Arquivo com requisicoes para criar e listar orders.

Entregavel: Repositorio unico no GitHub com Dockerfile, docker-compose.yaml, api.http e README (com comando de execucao e portas dos servicos). Todo o codigo na branch `main`.
