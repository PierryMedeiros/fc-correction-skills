---
name: corrige-temperatura-cep
description: >
  Corrige e avalia o desafio de Sistema de Temperatura por CEP em Go.
  TRIGGER quando: desafio de temperatura por CEP, clima por CEP, weather by zipcode,
  ViaCEP, WeatherAPI, Celsius, Fahrenheit, Kelvin, conversao de temperatura,
  Google Cloud Run, CEP, zipcode, temp_C, temp_F, temp_K, invalid zipcode,
  can not find zipcode, HTTP 422, HTTP 404.
  Palavras-chave: temperatura, CEP, clima, weather, ViaCEP, WeatherAPI, Celsius,
  Fahrenheit, Kelvin, Cloud Run, zipcode, Go, Docker, conversao, temp_C, temp_F, temp_K.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Sistema de Temperatura por CEP em Go

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Sistema de Temperatura por CEP".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

**Chaves de API:** Este desafio precisa de `WEATHER_API_KEY`. Carregue do arquivo `.env (nesta mesma pasta da skill)` e exporte antes de executar (ex: `export $(grep WEATHER_API_KEY .env (nesta mesma pasta da skill) | xargs)`). Se a chave estiver vazia, faca apenas analise estatica.

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento (se a chave estiver disponivel):
1. Construa a imagem: `docker build -t temp-cep-test .` no diretorio do projeto.
2. Execute o container: `docker run -d -p 8080:8080 -e WEATHER_API_KEY=$WEATHER_API_KEY temp-cep-test` (adapte a porta e variaveis conforme o projeto).
3. Teste CEP valido: `curl -s http://localhost:8080/{endpoint}/01001000` — deve retornar 200 com temp_C, temp_F, temp_K.
4. Teste CEP invalido (ex: 3 digitos): deve retornar 422 com "invalid zipcode".
5. Teste CEP inexistente (ex: 00000000): deve retornar 404 com "can not find zipcode".
6. Se houver testes automatizados (`*_test.go`), execute-os com `go test ./...` no diretorio do projeto.
7. Ao final, pare e remova o container.
8. Inclua os resultados da execucao na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `Dockerfile` (para containerizacao da aplicacao)
- Codigo-fonte da aplicacao em Go (ex: `main.go` ou estrutura de pastas como `cmd/`, `internal/`, etc)
- Arquivo(s) de teste automatizado (ex: `*_test.go`)
- `README.md`

### 2. Analise da Entrada (Validacao de CEP)
Verifique se o sistema valida a entrada do CEP:
- O sistema deve receber um CEP de **8 digitos**.
- Se o CEP nao tiver 8 digitos ou contiver caracteres invalidos, deve retornar **HTTP 422** com a mensagem `invalid zipcode`.
- Se o CEP tiver formato correto mas nao for encontrado na base de dados, deve retornar **HTTP 404** com a mensagem `can not find zipcode`.

### 3. Analise da Consulta de Localizacao
Verifique se o sistema realiza a busca do CEP para identificar a cidade:
- O codigo deve consumir uma API de CEP (ex: **ViaCEP** `viacep.com.br` ou similar) para obter o nome da cidade/localidade.

### 4. Analise da Consulta de Temperatura
Verifique se o sistema consulta a temperatura atual a partir da cidade obtida:
- O codigo deve consumir uma API de clima (ex: **WeatherAPI** `weatherapi.com` ou similar) para obter a temperatura em Celsius.

### 5. Analise da Conversao de Temperaturas
Verifique se o sistema retorna as temperaturas nos tres formatos exigidos:
- **Celsius** (temp_C): valor obtido da API de clima.
- **Fahrenheit** (temp_F): calculado como `C * 1.8 + 32`.
- **Kelvin** (temp_K): calculado como `C + 273`.
- O response body de sucesso deve ser um JSON com os campos `temp_C`, `temp_F` e `temp_K`, retornando **HTTP 200**.

### 6. Analise do Contrato da API
Verifique se o codigo implementa os tres cenarios do contrato:
- **Sucesso (200):** Retorna JSON com `temp_C`, `temp_F` e `temp_K`.
- **CEP invalido (422):** Retorna a mensagem `invalid zipcode`.
- **CEP nao encontrado (404):** Retorna a mensagem `can not find zipcode`.

### 7. Analise do Dockerfile
Verifique se existe um `Dockerfile` valido para containerizar a aplicacao:
- O Dockerfile deve ser capaz de construir e executar a aplicacao Go.
- Pode utilizar multi-stage build ou build simples.

### 8. Analise dos Testes Automatizados
Verifique se existem testes que comprovem o funcionamento:
- Testes de conversao de temperatura (Celsius para Fahrenheit e Kelvin).
- Testes de validacao de CEP (formato invalido, CEP nao encontrado).
- Testes de requisicao/integracao (opcional, mas desejavel).

### 9. Analise do README.md
Verifique se o README contem:
- A **URL do sistema rodando no Google Cloud Run** (endpoint ativo).
- Instrucoes de como rodar os testes.
- Instrucoes de como rodar a aplicacao localmente via Docker.

### 10. Verificacoes Adicionais
- O repositorio deve conter apenas um projeto (repositorio unico).
- Todo o codigo deve estar na branch `main`.

### 11. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O `Dockerfile` esta presente e e valido para construir a aplicacao Go.
- O sistema recebe um CEP e valida se possui 8 digitos (retorna 422 com `invalid zipcode` caso contrario).
- O sistema retorna 404 com `can not find zipcode` quando o CEP nao e encontrado.
- O sistema consulta uma API de CEP (ViaCEP ou similar) para obter a cidade.
- O sistema consulta uma API de clima (WeatherAPI ou similar) para obter a temperatura.
- O sistema retorna HTTP 200 com JSON contendo `temp_C`, `temp_F` e `temp_K`.
- As formulas de conversao estao corretas: `F = C * 1.8 + 32` e `K = C + 273`.
- Existem testes automatizados que validam as conversoes e/ou a validacao de CEP.
- O README contem a URL do Google Cloud Run, instrucoes de testes e instrucoes de execucao via Docker.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O README.md nao contem a URL do sistema no Google Cloud Run' ou 'Nao existem testes automatizados que validem as conversoes de temperatura']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Desenvolver um sistema em Go que receba um CEP, identifique a cidade correspondente e retorne o clima atual (temperatura em graus Celsius, Fahrenheit e Kelvin). O sistema deve estar publicado e acessivel no Google Cloud Run.

Tecnologias: Go, Docker, Google Cloud Run.

Requisitos Funcionais:
- Entrada: CEP valido de 8 digitos.
- Identificacao de Localizacao: Busca do CEP para encontrar o nome da cidade (ex: ViaCEP).
- Consulta de Clima: A partir da cidade, consultar a temperatura atual (ex: WeatherAPI).
- Conversao: Retornar temperaturas em Celsius, Fahrenheit e Kelvin.

Contrato da API:
- Sucesso (200): `{ "temp_C": 28.5, "temp_F": 83.3, "temp_K": 301.65 }`
- CEP invalido (422): `invalid zipcode`
- CEP nao encontrado (404): `can not find zipcode`

Formulas de Conversao:
- Celsius para Fahrenheit: F = C * 1.8 + 32
- Celsius para Kelvin: K = C + 273

Requisitos de Infraestrutura:
1. Dockerfile para containerizacao.
2. Deploy no Google Cloud Run (URL ativa).
3. Testes automatizados (conversoes e requisicoes).

Entregavel: Repositorio unico no GitHub com codigo na branch `main`. README com URL do Cloud Run, instrucoes de testes e execucao via Docker.
