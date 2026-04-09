---
name: corrige-multithreading-cep
description: >
  Corrige e avalia o desafio de Multithreading e busca paralela de CEP em Go.
  TRIGGER quando: desafio de multithreading, busca paralela, parallel request, race condition,
  goroutines, channels, select, BrasilAPI, ViaCEP, CEP paralelo, requisicoes simultaneas,
  timeout 1 segundo, API mais rapida, concorrencia, Go concurrency, goroutine race,
  buscador paralelo, cep-racer, parallel route, goparallelroute.
  Palavras-chave: multithreading, goroutine, channel, select, BrasilAPI, ViaCEP, CEP,
  paralelo, race, timeout, concorrencia, simultaneo, Go, net/http, requisicao paralela.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Multithreading e Busca Paralela de CEP em Go

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Multithreading - Busca Paralela de CEP".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Identifique o arquivo principal (main.go ou similar) e como o CEP e passado (argumento, flag, stdin, etc).
2. Execute a aplicacao com um CEP valido de teste, ex: `go run ./... 01001000` ou `go run main.go -cep=01001000` (adapte conforme o projeto).
3. Verifique se o output exibe: dados do endereco e qual API respondeu (BrasilAPI ou ViaCEP).
4. Se houver Dockerfile, pode tambem testar via Docker.
5. Inclua o resultado da execucao na sua avaliacao. Se a aplicacao falhar ou nao exibir o esperado, inclua os erros no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- Codigo-fonte da aplicacao em Go (ex: `main.go` ou estrutura de pastas como `cmd/`, `internal/`, etc)
- `README.md`

### 2. Analise das Requisicoes Simultaneas
Verifique se o sistema faz requisicoes para as duas APIs **ao mesmo tempo** (em paralelo):
- O codigo deve consumir **BrasilAPI**: `https://brasilapi.com.br/api/cep/v1/{cep}`
- O codigo deve consumir **ViaCEP**: `http://viacep.com.br/ws/{cep}/json/`
- As duas chamadas devem ser feitas de forma concorrente, utilizando **goroutines** (ex: `go func()`, `go nomeDaFuncao()`).

### 3. Analise da Race Condition (Corrida)
Verifique se o sistema aceita apenas a resposta da API que responder mais rapido:
- O codigo deve utilizar **channels** e/ou **select** para capturar a primeira resposta.
- A resposta da API mais lenta deve ser descartada.
- O uso de `select` com channels e o padrao esperado para implementar essa logica de corrida.

### 4. Analise do Output (Saida)
Verifique se o resultado e exibido na linha de comando (terminal) contendo:
- Os **dados do endereco** recebido da API vencedora.
- A **identificacao de qual API** entregou a resposta (BrasilAPI ou ViaCEP).

### 5. Analise do Timeout
Verifique se o sistema implementa um timeout de **1 segundo**:
- O codigo deve utilizar mecanismos de timeout (ex: `time.After(1 * time.Second)`, `context.WithTimeout`, `time.NewTimer`, ou similar).
- Se nenhuma das APIs responder dentro de 1 segundo, o sistema deve exibir um **erro de timeout**.
- O timeout deve estar integrado ao `select` ou ao contexto das requisicoes.

### 6. Analise das Tecnologias e Conceitos
Verifique se o codigo utiliza os conceitos exigidos:
- **Goroutines**: pelo menos 2 goroutines (uma para cada API).
- **Channels**: para comunicar o resultado das goroutines.
- **Select**: para capturar a primeira resposta ou o timeout.
- **Package net/http**: para fazer as requisicoes HTTP.

### 7. Analise do README.md
Verifique se o README contem:
- Instrucoes de como **executar** o projeto.
- Instrucoes de como **testar** a aplicacao.

### 8. Verificacoes Adicionais
- O repositorio deve conter apenas um projeto (repositorio unico).
- Todo o codigo deve estar na branch `main`.

### 9. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O codigo-fonte em Go e o README.md estao presentes.
- O sistema consome as duas APIs (BrasilAPI e ViaCEP) em paralelo usando goroutines.
- O sistema utiliza channels e/ou select para capturar apenas a resposta mais rapida.
- O output no terminal exibe os dados do endereco e identifica qual API respondeu.
- O sistema implementa timeout de 1 segundo (via `time.After`, `context.WithTimeout` ou equivalente).
- Se o timeout e atingido, o sistema exibe um erro de timeout.
- O README contem instrucoes de execucao e teste.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O sistema nao utiliza select para capturar a primeira resposta' ou 'O timeout de 1 segundo nao esta implementado']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Construir um sistema em Go que busca o endereco mais rapido entre duas APIs de CEP distintas, aplicando conhecimentos de Multithreading, concorrencia e timeouts.

Tecnologias: Go (Golang), Goroutines, Channels, Select, Package net/http.

APIs Alvo:
- BrasilAPI: `https://brasilapi.com.br/api/cep/v1/{cep}`
- ViaCEP: `http://viacep.com.br/ws/{cep}/json/`

Requisitos:
1. Requisicoes Simultaneas: Fazer requisicao para as duas APIs ao mesmo tempo (paralelamente) usando goroutines.
2. Race Condition: Aceitar apenas a resposta da API mais rapida e descartar a mais lenta, usando channels e select.
3. Output: Exibir no terminal os dados do endereco e qual API respondeu.
4. Timeout: Limite de 1 segundo. Se nenhuma API responder a tempo, exibir erro de timeout.

Entregavel: Repositorio unico no GitHub com codigo na branch `main`. README com instrucoes de execucao e teste.
