---
name: corrige-leilao-goroutines
description: >
  Corrige e avalia o desafio de Abertura e Fechamento do Leilao com Go Routines.
  TRIGGER quando: desafio de leilao, goroutines, go routines, concorrencia, auction,
  abertura e fechamento de leilao, channels, mutex, sync, tempo de expiracao, bid, lance,
  concurrency, goroutine, leilao automatico, fechamento automatico.
  Palavras-chave: leilao, auction, goroutine, go routine, concorrencia, channels, mutex,
  sync, bid, lance, fechamento automatico, Go, MongoDB, docker compose.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Abertura e Fechamento do Leilao com Go Routines

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Abertura e Fechamento do Leilao - Go Routines".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Execute `docker compose up -d --build` no diretorio do projeto.
2. Aguarde os containers subirem (use `sleep 10` ou verifique com `docker compose ps`).
3. Crie um leilao via API (adapte a porta e payload conforme o projeto).
4. Consulte o leilao criado e verifique se o status e Active/0.
5. Se houver testes automatizados, execute-os tambem.
6. Ao final, execute `docker compose down -v` para limpar.
7. Inclua os resultados da execucao na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `docker-compose.yml` ou `docker-compose.yaml` (ou `Dockerfile` que permita rodar o projeto)
- `internal/infra/database/auction/create_auction.go` (arquivo principal da implementacao)
- Arquivo(s) de teste que validem o fechamento automatico do leilao (ex: `create_auction_test.go` ou similar na pasta de auction ou em outra pasta de testes)
- `README.md`
- Configuracao de variavel de ambiente para duracao do leilao (ex: `AUCTION_DURATION`)

### 2. Analise do Fechamento Automatico (`create_auction.go`)
Este e o ponto central do desafio. Verifique se:
- **Goroutine:** Existe uma goroutine que e iniciada quando um leilao e criado, responsavel por monitorar o tempo e fechar o leilao automaticamente.
- **Duracao configuravel:** A duracao do leilao e obtida de uma variavel de ambiente (ex: `AUCTION_DURATION`) ou de uma configuracao externa, nao sendo hardcoded.
- **Update no banco:** Quando o tempo expira, a goroutine realiza um update no banco de dados alterando o status do leilao para fechado/closed.
- **Nao bloqueia:** A goroutine nao bloqueia a thread principal (a funcao de criacao retorna normalmente apos lancar a goroutine).

### 3. Analise dos Testes
Verifique se existe pelo menos um teste automatizado que:
- Cria um leilao.
- Aguarda o tempo configurado (ou um tempo reduzido para teste).
- Verifica se o status do leilao mudou automaticamente para fechado sem intervencao manual.
- O teste pode usar mock do banco de dados ou um banco real (ex: MongoDB em container de teste).

### 4. Analise do Docker/Docker Compose
Verifique se o projeto esta configurado para rodar via Docker ou Docker Compose:
- Deve existir `docker-compose.yml`/`docker-compose.yaml` ou ao menos um `Dockerfile`.
- O compose deve subir os servicos necessarios (aplicacao + MongoDB ou banco utilizado).

### 5. Analise do README.md
Verifique se o README contem:
- Instrucoes para rodar o projeto.
- Instrucoes para configurar as variaveis de ambiente de tempo (ex: `AUCTION_DURATION`).

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- O codigo deve estar baseado no repositorio `labs-auction-goexpert` (verifique se a estrutura de pastas segue o padrao: `internal/infra/database/auction/`, `internal/entity/`, etc).
- A validacao que impede lances em leiloes fechados ja existe no projeto base. Verifique se o aluno nao removeu ou quebrou essa logica.
- Verifique se ha uso adequado de mecanismos de concorrencia do Go (ex: `go func()`, `time.After`, `time.NewTimer`, `time.NewTicker`, `context.WithTimeout`, channels, etc).

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O arquivo `internal/infra/database/auction/create_auction.go` contem a implementacao de uma goroutine para fechamento automatico do leilao.
- A duracao do leilao e configuravel via variavel de ambiente.
- A goroutine realiza o update no banco de dados para fechar o leilao apos o tempo expirar.
- A goroutine nao bloqueia a thread principal.
- Existe pelo menos um teste automatizado que valida o fechamento automatico.
- O projeto esta configurado para rodar via Docker/Docker Compose.
- O README contem instrucoes de execucao e configuracao de variaveis de ambiente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'Nao existe teste automatizado para o fechamento do leilao' ou 'A duracao do leilao esta hardcoded em vez de vir de variavel de ambiente']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Adicionar fechamento automatico ao sistema de leiloes usando Goroutines. O leilao deve ser encerrado automaticamente apos um tempo pre-definido.

Base do Projeto: https://github.com/devfullcycle/labs-auction-goexpert

Tecnologias: Go, Docker/Docker Compose, MongoDB.

Requisitos:
1. Modificar `internal/infra/database/auction/create_auction.go` para incluir agendamento de fechamento.
2. Duracao do leilao configuravel via variavel de ambiente (ex: AUCTION_DURATION).
3. Goroutine iniciada na criacao do leilao que monitora o tempo e fecha o leilao (update no banco, status "Closed").
4. Teste automatizado que cria um leilao, aguarda o tempo e verifica se o status mudou para fechado.
5. Projeto rodavel via Docker/Docker Compose.
6. README com instrucoes de execucao e configuracao de variaveis de ambiente.
