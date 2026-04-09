---
name: corrige-client-server-api
description: >
  Corrige e avalia o desafio de Client-Server-API em Go.
  TRIGGER quando: desafio de client server API, cliente servidor, cotacao dolar, USD-BRL,
  context.WithTimeout, timeout, SQLite, servidor HTTP Go, client.go, server.go,
  cotacao.txt, cambio, economia API, HTTP client server.
  Palavras-chave: client, server, API, Go, cotacao, dolar, USD-BRL, context, timeout,
  SQLite, HTTP, server.go, client.go, cotacao.txt, cambio, economia, awesomeapi.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Client-Server-API em Go

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Client-Server-API em Go".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Identifique os arquivos server.go e client.go (podem estar em subpastas como `server/` e `client/`).
2. Execute `go run` do server em background (ex: `go run server/server.go &` ou `go run server.go &`).
3. Aguarde 2 segundos para o servidor iniciar.
4. Execute `go run` do client (ex: `go run client/client.go` ou `go run client.go`).
5. Verifique se o arquivo `cotacao.txt` foi criado e contem o formato `Dólar: {valor}` (ou `Dolar: {valor}`).
6. Pare o servidor em background.
7. Inclua os resultados da execucao na sua avaliacao. Se o servidor ou cliente falharem, inclua os erros no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos obrigatorios existem:
- `server.go` (servidor HTTP)
- `client.go` (cliente HTTP)
- `README.md` (instrucoes de execucao)

### 2. Analise do Server (`server.go`)
Verifique se o servidor atende aos seguintes requisitos:
- **Porta:** Opera na porta **8080**.
- **Endpoint:** Expoe o endpoint `/cotacao`.
- **Consumo de API Externa:** Ao receber uma requisicao em `/cotacao`, consome a API de cambio `https://economia.awesomeapi.com.br/json/last/USD-BRL`.
- **Timeout da API Externa:** O timeout maximo para chamar a API externa deve ser de **200ms**, utilizando o pacote `context` (ex: `context.WithTimeout`).
- **Persistencia em SQLite:** O servidor registra cada cotacao recebida em um banco de dados **SQLite**.
- **Timeout do Banco de Dados:** O timeout maximo para persistir os dados no banco deve ser de **10ms**, utilizando o pacote `context` (ex: `context.WithTimeout`).
- **Resposta JSON:** O endpoint retorna o resultado da cotacao em formato JSON para o cliente.
- **Logs de Timeout:** Caso os timeouts (API ou banco) sejam excedidos, o erro deve ser logado no console do servidor.

### 3. Analise do Client (`client.go`)
Verifique se o cliente atende aos seguintes requisitos:
- **Requisicao HTTP:** Realiza uma requisicao ao endpoint `/cotacao` do servidor local (porta 8080).
- **Timeout da Requisicao:** O timeout maximo para receber o resultado do servidor deve ser de **300ms**, utilizando o pacote `context` (ex: `context.WithTimeout`).
- **Processamento do JSON:** Recebe apenas o valor atual do cambio (campo `bid` do JSON).
- **Gravacao em Arquivo:** Salva a cotacao em um arquivo chamado `cotacao.txt` no formato: `Dolar: {valor}`.
- **Logs de Timeout:** Caso o timeout de 300ms seja excedido, o erro deve ser logado no console do cliente.

### 4. Analise do Uso de Context
Este e um ponto central do desafio. Verifique se:
- O `server.go` utiliza `context.WithTimeout` (ou equivalente do pacote `context`) com **200ms** para a chamada a API externa.
- O `server.go` utiliza `context.WithTimeout` (ou equivalente do pacote `context`) com **10ms** para a persistencia no banco de dados.
- O `client.go` utiliza `context.WithTimeout` (ou equivalente do pacote `context`) com **300ms** para a requisicao ao servidor.
- Verifique se ha imports do pacote `context` e uso adequado de `ctx`, `cancel`, `defer cancel()`, etc.

### 5. Analise do README.md
Verifique se o README contem:
- Instrucoes de como rodar o servidor (`server.go`).
- Instrucoes de como rodar o cliente (`client.go`).

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas um projeto (repositorio unico).
- Todo o codigo deve estar na branch `main`.
- Verifique se o codigo utiliza a biblioteca SQLite adequadamente (ex: `mattn/go-sqlite3`, `modernc.org/sqlite`, ou similar).

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Os arquivos `server.go`, `client.go` e `README.md` estao presentes.
- O `server.go` opera na porta 8080 e expoe o endpoint `/cotacao`.
- O `server.go` consome a API externa de cambio USD-BRL.
- O `server.go` utiliza `context.WithTimeout` com 200ms para a chamada a API externa.
- O `server.go` persiste a cotacao em banco de dados SQLite.
- O `server.go` utiliza `context.WithTimeout` com 10ms para a persistencia no banco.
- O `server.go` retorna a cotacao em JSON.
- O `client.go` faz requisicao ao endpoint `/cotacao` do servidor.
- O `client.go` utiliza `context.WithTimeout` com 300ms para a requisicao.
- O `client.go` extrai o campo `bid` e salva em `cotacao.txt` no formato `Dolar: {valor}`.
- Erros de timeout sao logados no console tanto no servidor quanto no cliente.
- O README contem instrucoes de execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O server.go nao utiliza context.WithTimeout com 200ms para a chamada a API externa' ou 'O client.go nao salva a cotacao no arquivo cotacao.txt no formato exigido']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Criar dois sistemas interligados (client.go e server.go) em Go que trocam informacoes respeitando limites estritos de tempo (timeout), aplicando conhecimentos de HTTP, Contextos, Banco de Dados e Manipulacao de Arquivos.

Tecnologias: Go, SQLite, HTTP, Context.

Server.go:
- Servidor HTTP na porta 8080, endpoint `/cotacao`.
- Consome API externa: `https://economia.awesomeapi.com.br/json/last/USD-BRL` (timeout: 200ms via context).
- Persiste cotacao em SQLite (timeout: 10ms via context).
- Retorna cotacao em JSON. Loga erros de timeout no console.

Client.go:
- Requisicao HTTP ao endpoint `/cotacao` do servidor (timeout: 300ms via context).
- Extrai campo `bid` do JSON recebido.
- Salva em `cotacao.txt` no formato: `Dolar: {valor}`.
- Loga erros de timeout no console.

Entregavel: Repositorio unico no GitHub com `server.go`, `client.go` e `README.md` com instrucoes de execucao. Todo o codigo na branch `main`.
