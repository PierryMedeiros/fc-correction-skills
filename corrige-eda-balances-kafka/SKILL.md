---
name: corrige-eda-balances-kafka
description: >
  Corrige e avalia o desafio de EDA - Microsservico de Balances consumidor Kafka.
  TRIGGER quando: desafio de EDA, event driven architecture, microsservico balances,
  consumidor kafka, wallet core, saldo de contas, balances service, kafka consumer,
  fc3-eda, criacao de microservice, microsservico kafka, balances account_id,
  porta 3003, GET /balances.
  Palavras-chave: EDA, event driven, kafka, balances, wallet core, microsservico,
  consumidor, saldo, account_id, porta 3003, docker compose, transacoes,
  fc3-eda, criacao de microservice, microservice, kafka consumer.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - EDA: Microsservico de Balances (Consumidor Kafka)

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "EDA: Microsservico de Balances (Consumidor Kafka)".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Execute `docker compose up -d --build` no diretorio do projeto.
2. Aguarde os containers subirem (use `sleep 20` ou verifique com `docker compose ps` — Kafka pode demorar).
3. Teste o endpoint: `curl -s http://localhost:3003/balances/{account_id}` — use um account_id dos seeds/dados ficticios (verifique nos arquivos de seed ou migration qual ID usar).
4. Verifique se o endpoint retorna o saldo da conta.
5. Ao final, execute `docker compose down -v` para limpar.
6. Inclua os resultados da execucao na sua avaliacao. Se o `docker compose up` falhar ou o endpoint nao responder, inclua os erros no motivo da reprovacao.

**IMPORTANTE:** O foco de correcao e na **arquitetura** (fluxo de eventos funcionando) e na **automacao** (Docker), nao na qualidade interna do codigo. A linguagem e livre.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios existem:
- `docker-compose.yml` ou `docker-compose.yaml` (orquestrando todo o ecossistema).
- Codigo do microsservico **Balances** (pasta dedicada, em qualquer linguagem).
- Codigo do microsservico **Wallet Core** (pode ser o projeto base do curso ou adaptado).
- Arquivo `api.http` (ou colecao Postman) com chamadas prontas para teste.
- `README.md` com instrucoes de execucao.

### 2. Analise do Docker Compose
Verifique se o `docker-compose` sobe o ecossistema completo:
- **Kafka** (e Zookeeper se necessario).
- **Wallet Core** (microsservico produtor de eventos).
- **Balances Service** (microsservico consumidor — o desafio do aluno).
- **Banco(s) de dados** para ambos os microsservicos.
- As migracoes e seeds devem ser executadas automaticamente ao subir (sem scripts manuais).

### 3. Analise do Microsservico Balances
Verifique se o microsservico Balances:
- **Se conecta ao Kafka** e escuta os topicos de transacoes do Wallet Core.
- **Persiste o saldo** atualizado de cada conta em um banco de dados proprio.
- **Expoe o endpoint** `GET /balances/{account_id}` (ou equivalente como `/balances/:account_id`).
- **Roda na porta 3003**.
- Retorna o saldo atual da conta solicitada.

### 4. Analise do Consumo de Eventos Kafka
Verifique no codigo do Balances se:
- Ha configuracao de conexao com Kafka (broker, topic, consumer group).
- Ha logica para processar eventos de transacao recebidos do Wallet Core.
- O saldo e atualizado no banco apos receber o evento.

### 5. Analise da Inicializacao Automatica
Verifique se ao rodar `docker compose up -d`:
- As tabelas sao criadas automaticamente (migracoes).
- Dados ficticios sao inseridos (seeds) para permitir testes imediatos.
- Nao e necessario rodar scripts manuais apos os containers subirem.

### 6. Analise do Arquivo api.http
Verifique se existe um arquivo `api.http` (ou colecao Postman) com:
- Chamada para `GET /balances/{account_id}` no microsservico Balances (porta 3003).
- Opcionalmente, chamadas para o Wallet Core para criar transacoes.

### 7. Analise do README.md
Verifique se contem:
- Instrucoes de como subir o projeto (`docker compose up`).
- Descricao basica da arquitetura (Wallet Core + Balances + Kafka).

### 8. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 9. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O Docker Compose sobe o ecossistema completo (Kafka, Wallet Core, Balances, bancos de dados).
- O microsservico Balances se conecta ao Kafka e consome eventos de transacao.
- O microsservico Balances persiste saldos em banco de dados proprio.
- O endpoint `GET /balances/{account_id}` existe e roda na porta 3003.
- As migracoes e seeds sao executadas automaticamente com `docker compose up`.
- Existe arquivo `api.http` ou colecao Postman com chamadas de teste.
- O README contem instrucoes de execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O endpoint GET /balances/{account_id} nao esta implementado' ou 'O Docker Compose nao inclui o Kafka' ou 'O microsservico Balances nao consome eventos do Kafka']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Desenvolver um microsservico Balances que consome eventos de transacao do Wallet Core via Kafka, atualiza saldos em banco proprio, e expoe consulta via API.

Tecnologias: Linguagem livre, Apache Kafka, Docker/Docker Compose.

Requisitos:
1. Microsservico Balances conectado ao Kafka como consumidor.
2. Persistencia de saldo atualizado por conta em banco proprio.
3. Endpoint GET /balances/{account_id} na porta 3003.
4. Docker Compose orquestrando: Kafka, Wallet Core, Balances, bancos de dados.
5. Migracoes e seeds automaticos ao subir.
6. Arquivo api.http com chamadas de teste.
7. README com instrucoes.

Foco de correcao: Arquitetura (fluxo de eventos) e automacao (Docker), nao qualidade interna do codigo.

Entregavel: Repositorio unico no GitHub com projeto completo. Branch `main`.
