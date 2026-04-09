---
name: corrige-tracing-distribuido
description: >
  Corrige e avalia o desafio de Tracing Distribuido e Span.
  TRIGGER quando: desafio de tracing distribuido, span, OpenTelemetry, OTEL, Jaeger, Zipkin,
  observabilidade, observability, trace, distributed tracing, instrumentacao, telemetria,
  propagacao de contexto, context propagation, collector, exporter, microservicos com tracing.
  Palavras-chave: tracing, span, OpenTelemetry, OTEL, Jaeger, Zipkin, observabilidade,
  distributed tracing, collector, exporter, Go, docker compose, microservicos.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Tracing Distribuido e Span

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Tracing Distribuido e Span".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

**Chaves de API:** Este desafio precisa de `WEATHER_API_KEY`. Carregue do arquivo `.env (nesta mesma pasta da skill)` e exporte antes de executar (ex: `export $(grep WEATHER_API_KEY .env (nesta mesma pasta da skill) | xargs)`). Se a chave estiver vazia, faca apenas analise estatica.

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento (se a chave estiver disponivel):
1. Exporte a WEATHER_API_KEY e crie/atualize o `.env` do projeto se necessario.
2. Execute `docker compose up -d --build` no diretorio do projeto.
3. Aguarde os containers subirem (use `sleep 15` ou verifique com `docker compose ps`).
4. Teste CEP valido: `curl -s -X POST http://localhost:8080/ -H 'Content-Type: application/json' -d '{"cep":"01001000"}'` — deve retornar 200 com city, temp_C, temp_F, temp_K.
5. Teste CEP invalido: `curl -s -X POST http://localhost:8080/ -H 'Content-Type: application/json' -d '{"cep":"123"}'` — deve retornar 422 com "invalid zipcode".
6. Teste CEP inexistente: `curl -s -X POST http://localhost:8080/ -H 'Content-Type: application/json' -d '{"cep":"00000000"}'` — deve retornar 404 com "can not find zipcode".
7. Ao final, execute `docker compose down -v` para limpar.
8. Inclua os resultados da execucao na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `docker-compose.yml` ou `docker-compose.yaml`
- Codigo do Servico A (pasta ou modulo dedicado, ex: `service-a/`, `servico-a/`, `input/`, ou similar)
- Codigo do Servico B (pasta ou modulo dedicado, ex: `service-b/`, `servico-b/`, `orquestracao/`, ou similar)
- Configuracao do OTEL Collector (ex: `otel-collector-config.yaml`, `collector.yaml`, ou similar)
- `README.md`
- Dockerfiles para os servicos A e B

### 2. Analise do Docker Compose
Verifique se o `docker-compose.yml`/`docker-compose.yaml` sobe os 4 servicos obrigatorios:
- **Servico A** (porta HTTP exposta para receber requisicoes)
- **Servico B** (comunicacao interna com o Servico A)
- **OTEL Collector** (recebe dados de tracing dos servicos)
- **Zipkin** (visualizacao dos traces)

### 3. Analise do Servico A (Input)
- Aceita requisicoes via **POST** com payload JSON `{ "cep": "29902555" }`.
- Valida que o CEP e uma **string com exatamente 8 digitos**.
- Se o CEP for invalido (nao tem 8 digitos ou nao e string), retorna **HTTP 422** com mensagem `invalid zipcode`.
- Se o CEP for valido, **encaminha a requisicao para o Servico B via HTTP**.

### 4. Analise do Servico B (Orquestracao)
- Recebe o CEP valido do Servico A.
- **Consulta API externa de localizacao** (ex: ViaCEP) para obter o nome da cidade.
- **Consulta API externa de clima** (ex: WeatherAPI) para obter a temperatura atual.
- Realiza as **conversoes de temperatura**:
  - Celsius para Fahrenheit: `F = C * 1.8 + 32`
  - Celsius para Kelvin: `K = C + 273`
- Respostas:
  - **Sucesso (200):** Retorna JSON com `city`, `temp_C`, `temp_F`, `temp_K`.
  - **CEP invalido (422):** Retorna `invalid zipcode`.
  - **CEP nao encontrado (404):** Retorna `can not find zipcode`.

### 5. Analise de Observabilidade (OTEL + Zipkin)
- **Tracing Distribuido:** Ambos os servicos devem estar instrumentados com OpenTelemetry, permitindo visualizar no Zipkin o fluxo completo: `Request -> Servico A -> Servico B`.
- **Spans Manuais:** O codigo deve criar spans especificos para:
  - Busca de CEP (chamada a API externa de localizacao).
  - Busca de Temperatura (chamada a API externa de clima).
- **OTEL Collector:** Deve existir configuracao do collector para receber dados dos servicos e enviar ao Zipkin.
- Verifique se ha imports e uso de bibliotecas de OpenTelemetry no codigo Go (ex: `go.opentelemetry.io/otel`, `go.opentelemetry.io/otel/trace`).
- Verifique se ha propagacao de contexto entre Servico A e Servico B (ex: uso de `otel/propagation`, injecao de headers de trace na chamada HTTP do Servico A para o Servico B).

### 6. Analise do README.md
Verifique se o README contem:
- Instrucoes de como realizar a requisicao POST no Servico A.
- Instrucoes de como acessar o Zipkin para visualizar os traces.

### Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Todos os arquivos e diretorios obrigatorios estao presentes.
- O `docker-compose` sobe os 4 servicos (Servico A, Servico B, OTEL Collector, Zipkin).
- O Servico A valida o CEP (8 digitos, string) e encaminha ao Servico B.
- O Servico B consulta localizacao, consulta clima, faz conversoes e retorna os codigos HTTP corretos (200, 422, 404).
- Ambos os servicos estao instrumentados com OpenTelemetry (imports e uso de tracer/spans).
- Existem spans manuais para busca de CEP e busca de temperatura.
- Ha propagacao de contexto de tracing entre Servico A e Servico B.
- O README instrui como fazer a requisicao e como acessar o Zipkin.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O Servico B nao cria spans manuais para a busca de CEP e temperatura' ou 'O docker-compose nao inclui o OTEL Collector']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Desenvolver um sistema distribuido em Go composto por dois microsservicos (Servico A e Servico B) que cooperam para consultar o clima de uma cidade baseada no CEP, com observabilidade via OpenTelemetry e Zipkin.

Tecnologias: Go, Docker Compose, OpenTelemetry, Zipkin.

Arquitetura:
- Servico A (Input): Recebe POST com CEP, valida (8 digitos, string), encaminha ao Servico B. Se invalido: HTTP 422 "invalid zipcode".
- Servico B (Orquestracao): Recebe CEP, consulta ViaCEP para cidade, consulta WeatherAPI para temperatura, converte para Celsius/Fahrenheit/Kelvin. Sucesso: HTTP 200 com city, temp_C, temp_F, temp_K. CEP invalido: 422 "invalid zipcode". CEP nao encontrado: 404 "can not find zipcode".
- OTEL + Zipkin: Tracing distribuido com fluxo Request -> Servico A -> Servico B. Spans manuais para busca de CEP e busca de temperatura. OTEL Collector como intermediario.

Docker Compose deve subir: Servico A, Servico B, OTEL Collector, Zipkin.

README deve conter: instrucoes de como fazer POST no Servico A e como acessar o Zipkin.
