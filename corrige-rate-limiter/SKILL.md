---
name: corrige-rate-limiter
description: >
  Corrige e avalia o desafio de Rate Limiter em Go.
  TRIGGER quando: desafio de rate limiter, rate limiting, limitador de taxa, middleware,
  Redis, API_KEY, token, IP, bloqueio, HTTP 429, too many requests, strategy pattern,
  limite de requisicoes, throttling, controle de trafego.
  Palavras-chave: rate limiter, rate limiting, middleware, Redis, API_KEY, token, IP,
  bloqueio, HTTP 429, too many requests, strategy, Go, docker compose, limite, throttling.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Rate Limiter em Go

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Rate Limiter em Go".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Execute `docker compose up -d --build` no diretorio do projeto.
2. Aguarde os containers subirem (use `sleep 10` ou verifique com `docker compose ps`).
3. Teste limite por IP: envie requisicoes em loop com `for i in $(seq 1 20); do curl -s -o /dev/null -w "%{http_code}\n" http://localhost:8080/; done` e verifique se eventualmente retorna 429.
4. Teste limite por Token: envie requisicoes com header `API_KEY` e verifique a precedencia Token > IP.
5. Verifique se a mensagem de bloqueio contem: "you have reached the maximum number of requests or actions allowed within a certain time frame".
6. Se houver testes automatizados, execute-os tambem.
7. Ao final, execute `docker compose down -v` para limpar.
8. Inclua os resultados da execucao na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `docker-compose.yml` ou `docker-compose.yaml`
- `Dockerfile` (para a aplicacao)
- Arquivo(s) de configuracao (`.env` ou `.env.example` na raiz do projeto)
- Codigo-fonte da aplicacao (ex: `main.go` ou estrutura de pastas como `cmd/`, `internal/`, etc)
- Arquivo(s) de teste automatizado
- `README.md`

### 2. Analise do Middleware de Rate Limiting
Verifique se a logica do Rate Limiter esta implementada como um **middleware** que envolve o servidor web:
- O middleware deve interceptar as requisicoes antes de chegarem aos handlers.
- Deve verificar o limite por **IP** e por **Token** (header `API_KEY`).
- **Regra de Precedencia:** As configuracoes do Token devem se sobrepor as do IP. Se um token tiver limite proprio, esse limite deve ser respeitado em vez do limite por IP.

### 3. Analise da Limitacao por IP
- O sistema deve restringir o numero maximo de requisicoes por segundo de um unico endereco IP.
- O limite deve ser configuravel via variavel de ambiente.

### 4. Analise da Limitacao por Token
- O sistema deve restringir o numero maximo de requisicoes por segundo baseado em um token de acesso unico.
- O token deve ser verificado no header `API_KEY`.
- O limite do token deve ter precedencia sobre o limite do IP.

### 5. Analise do Comportamento de Bloqueio
Verifique se, quando o limite e excedido:
- O servidor retorna **HTTP 429** (Too Many Requests).
- O corpo da resposta contem a mensagem: `you have reached the maximum number of requests or actions allowed within a certain time frame`.
- O IP ou Token infrator fica bloqueado por um tempo configuravel. Durante o bloqueio, todas as novas requisicoes devem ser rejeitadas com 429.

### 6. Analise da Persistencia (Redis)
- As informacoes de contagem e controle de tempo devem ser armazenadas no **Redis**.
- Verifique se o codigo utiliza uma biblioteca Redis adequada (ex: `go-redis`, `redigo`, ou similar).
- **Padrao Strategy:** Verifique se a persistencia esta implementada usando o padrao Strategy (ou equivalente com interface), permitindo trocar o Redis por outro mecanismo facilmente. Deve existir uma interface que abstraia as operacoes de persistencia, com a implementacao concreta usando Redis.

### 7. Analise do Docker/Docker Compose
Verifique se:
- O `docker-compose` sobe pelo menos 2 servicos: **aplicacao** (na porta 8080) e **Redis**.
- Existe um `Dockerfile` para a aplicacao.
- O projeto funciona apenas com `docker compose up`, sem comandos adicionais.

### 8. Analise da Configuracao
Verifique se as seguintes configuracoes sao feitas via variaveis de ambiente (ou arquivo `.env`):
- Limite maximo de requisicoes por segundo (por IP e/ou por Token).
- Tempo de bloqueio em caso de excesso.
- Configuracoes de conexao com Redis (host, porta, etc).

### 9. Analise dos Testes Automatizados
Verifique se existem testes que demonstrem:
- A eficacia do limiter (requisicoes sao bloqueadas apos atingir o limite).
- A logica de precedencia (Token sobrepoe IP).

### 10. Analise do README.md
Verifique se o README contem:
- Instrucoes de como configurar o limiter (variaveis de ambiente).
- Instrucoes de como alterar as estrategias de persistencia.
- Instrucoes de como executar o projeto.

### 11. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Todos os arquivos obrigatorios estao presentes (docker-compose, Dockerfile, .env, README, testes).
- O Rate Limiter esta implementado como middleware.
- O sistema limita requisicoes por IP e por Token (header `API_KEY`).
- O Token tem precedencia sobre o IP.
- Quando o limite e excedido, retorna HTTP 429 com a mensagem exigida.
- O IP/Token infrator fica bloqueado por tempo configuravel.
- A persistencia utiliza Redis.
- O padrao Strategy (ou interface equivalente) esta implementado para a camada de persistencia.
- O Docker Compose sobe a aplicacao (porta 8080) e o Redis.
- As configuracoes sao feitas via variaveis de ambiente ou `.env`.
- Existem testes automatizados que validam o limiter e a precedencia Token > IP.
- O README contem instrucoes de configuracao e execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'Nao existem testes automatizados que validem a precedencia do Token sobre o IP' ou 'A persistencia nao utiliza o padrao Strategy para abstrair o Redis']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Desenvolver um Rate Limiter em Go que funcione como middleware para controlar o fluxo de requisicoes de um servico web, limitando o trafego com base no IP ou em um Token de acesso, utilizando Redis para persistencia.

Tecnologias: Go, Redis, Docker/Docker Compose.

Regras de Negocio:
- Limitacao por IP: Restringe o numero maximo de requisicoes por segundo de um unico endereco IP.
- Limitacao por Token: Restringe o numero maximo de requisicoes por segundo baseado em um token de acesso unico (header `API_KEY`). O limite do Token tem precedencia sobre o do IP.
- Bloqueio: Quando o limite e excedido, retorna HTTP 429 com a mensagem "you have reached the maximum number of requests or actions allowed within a certain time frame". O IP/Token infrator fica bloqueado por tempo configuravel.

Requisitos Tecnicos:
1. Middleware: Logica do Rate Limiter implementada como middleware.
2. Persistencia em Redis: Contagem e controle de tempo armazenados no Redis.
3. Padrao Strategy: Interface que abstraia a persistencia, permitindo trocar o Redis por outro mecanismo facilmente.
4. Desacoplamento: Logica de negocio do limiter separada da logica do middleware.
5. Configuracao via variaveis de ambiente ou `.env`: limite de requisicoes, tempo de bloqueio, conexao Redis.
6. Docker Compose: Sobe aplicacao (porta 8080) e Redis.
7. Testes automatizados: Demonstram eficacia do limiter e precedencia Token > IP.
8. README: Instrucoes de configuracao, estrategias e execucao.

Entregavel: Repositorio unico com Dockerfile, docker-compose.yaml, `.env`, testes e README. Todo o codigo na branch `main`. O avaliador deve conseguir rodar o projeto e os testes usando apenas Docker/Docker Compose.
