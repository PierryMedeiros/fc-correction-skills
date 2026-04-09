---
name: corrige-stress-test-go
description: >
  Corrige e avalia o desafio de Sistema de Stress Test (teste de carga) em Go.
  TRIGGER quando: desafio de stress test, teste de carga, load test, CLI teste,
  --url, --requests, --concurrency, chamadas simultaneas, requisicoes HTTP,
  relatorio, docker run, teste de performance, benchmark HTTP.
  Palavras-chave: stress test, teste de carga, load test, CLI, --url, --requests,
  --concurrency, Go, Docker, relatorio, requisicoes HTTP, concorrencia,
  goroutines, status code, performance, benchmark.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Sistema de Stress Test em Go

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Sistema de Stress Test (Teste de Carga) em Go".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Construa a imagem: `docker build -t stress-test-eval .` no diretorio do projeto.
2. Execute o teste de carga: `docker run --rm stress-test-eval --url=http://google.com --requests=10 --concurrency=2` (use valores baixos para nao sobrecarregar).
3. Verifique se o relatorio no output contem: tempo total, total de requests, requests com status 200, e distribuicao de outros status codes.
4. Se houver testes automatizados (`*_test.go`), execute-os com `go test ./...`.
5. Ao final, remova a imagem criada.
6. Inclua os resultados da execucao na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `Dockerfile` (para construcao da imagem Docker)
- Codigo-fonte da aplicacao em Go (ex: `main.go` ou estrutura de pastas como `cmd/`, `internal/`, etc)
- `README.md`

### 2. Analise dos Parametros de Entrada (CLI)
Verifique se a aplicacao aceita os seguintes parametros via linha de comando:
- `--url`: URL do servico a ser testado.
- `--requests`: Numero total de requisicoes a serem realizadas.
- `--concurrency`: Numero de chamadas simultaneas.
- Os parametros devem ser parseados corretamente (ex: usando `flag`, `cobra`, `pflag`, ou `os.Args`).

### 3. Analise da Execucao do Teste
Verifique se o codigo implementa:
- **Requisicoes HTTP:** O sistema realiza requisicoes HTTP para a URL especificada (usando `net/http` ou biblioteca equivalente).
- **Concorrencia:** As requisicoes sao distribuidas de acordo com o nivel de concorrencia definido (ex: usando goroutines, worker pool, channels, ou similar).
- **Total de requisicoes:** O numero total de requisicoes (`--requests`) deve ser cumprido exatamente, independentemente do nivel de concorrencia.

### 4. Analise do Relatorio
Verifique se, ao final da execucao, o sistema gera um relatorio no console contendo:
- **Tempo total** gasto na execucao.
- **Quantidade total** de requests realizados.
- **Quantidade de requests com status HTTP 200.**
- **Distribuicao de outros codigos de status HTTP** (ex: quantidade de 404, 500, etc).

### 5. Analise do Dockerfile
Verifique se:
- Existe um `Dockerfile` que constroi a imagem da aplicacao.
- A imagem deve ser executavel no formato: `docker run <imagem> --url=http://example.com --requests=1000 --concurrency=10`.
- O Dockerfile deve gerar um binario executavel (ex: multi-stage build ou build direto).
- O `ENTRYPOINT` ou `CMD` deve apontar para o binario da aplicacao, permitindo passar os parametros via linha de comando.

### 6. Analise do README.md
Verifique se o README contem:
- Instrucoes de como **buildar** a imagem Docker (ex: `docker build`).
- Instrucoes de como **executar** o comando de teste (ex: `docker run <imagem> --url=... --requests=... --concurrency=...`).

### 7. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (nao deve ser um monorepo com outros desafios).
- Todo o codigo deve estar na branch `main`.

### 8. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Os arquivos obrigatorios estao presentes (Dockerfile, codigo-fonte Go, README).
- A aplicacao aceita os parametros `--url`, `--requests` e `--concurrency` via CLI.
- O sistema realiza requisicoes HTTP para a URL especificada.
- As requisicoes sao distribuidas de forma concorrente (goroutines, worker pool, etc).
- O numero total de requisicoes e cumprido exatamente.
- O relatorio exibe: tempo total, total de requests, requests com status 200, e distribuicao de outros status codes.
- O Dockerfile constroi a imagem corretamente e permite execucao via `docker run`.
- O README contem instrucoes de build e execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O relatorio nao exibe a distribuicao de outros codigos de status HTTP' ou 'O Dockerfile nao permite passar parametros via linha de comando']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Criar um sistema de CLI (Command Line Interface) em Go para realizar testes de carga em servicos web. O usuario fornece a URL do servico, o numero total de requisicoes e a quantidade de chamadas simultaneas. Ao final, o sistema gera um relatorio detalhado da execucao.

Tecnologias: Go (Golang), Docker.

Parametros de Entrada (CLI):
- `--url`: URL do servico a ser testado.
- `--requests`: Numero total de requisicoes a serem realizadas.
- `--concurrency`: Numero de chamadas simultaneas.

Requisitos Tecnicos:
1. Execucao do Teste: Realizar requisicoes HTTP para a URL especificada. Distribuir as requisicoes de acordo com o nivel de concorrencia. Garantir que o numero total de requisicoes seja cumprido exato.
2. Geracao de Relatorio: Tempo total gasto na execucao. Quantidade total de requests realizados. Quantidade de requests com status HTTP 200. Distribuicao de outros codigos de status HTTP (ex: 404, 500, etc).
3. Execucao via Docker: `docker run <imagem> --url=http://google.com --requests=1000 --concurrency=10`.

Entregavel: Repositorio unico no GitHub com codigo-fonte, Dockerfile e README com instrucoes de build e execucao. Todo o codigo na branch `main`.
