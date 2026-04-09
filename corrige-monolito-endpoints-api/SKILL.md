---
name: corrige-monolito-endpoints-api
description: >
  Corrige e avalia o desafio de Sistemas Monoliticos - Criacao de API em TypeScript.
  TRIGGER quando: desafio de sistemas monoliticos, monolito, API monolito, fc-monolito,
  checkout, invoice, products, clients, Express, Supertest, e2e monolito,
  camada de API, web layer, endpoints REST monolito.
  Palavras-chave: monolito, monolitico, API, Express, Supertest, checkout, invoice,
  products, clients, POST, GET, endpoints, e2e, TypeScript, fc-monolito,
  sistemas monoliticos, camada de API, nota fiscal, pedido, compra.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Sistemas Monoliticos: API e Testes E2E

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Sistemas Monoliticos: API e Testes End-to-End".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test`.
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se o projeto utiliza a estrutura base do repositorio `fc-monolito`.
O repositorio do aluno DEVE seguir a organizacao modular do curso. Ter arquivos/pastas a mais e aceitavel (desde que faca sentido), mas ter a menos ou de forma desorganizada e motivo de reprovacao.

**Estrutura minima obrigatoria de pastas (baseada no repo oficial do curso):**
```
src/
  modules/
    @shared/
      domain/entity/       (base-entity ou similar)
      domain/value-object/ (id, address, etc)
    client-adm/
      domain/    facade/    factory/    gateway/
      repository/    usecase/add-client/    usecase/find-client/
    product-adm/
      domain/    facade/    factory/    gateway/
      repository/    usecase/add-product/    usecase/check-stock/
    store-catalog/
      domain/    facade/    factory/    gateway/
      repository/    usecase/find-product/    usecase/find-all-products/
    payment/
      domain/    facade/    factory/    gateway/
      repository/    usecase/process-payment/
    checkout/        (modulo de checkout/pedido)
    invoice/         (modulo de invoice/nota fiscal)
```

O aluno deve ter adicionado:
- Uma camada de API/Web (ex: rotas Express em algum local do projeto).
- Arquivo(s) de teste E2E para a API.
- `README.md` com instrucoes de execucao.

**Se a estrutura do repositorio estiver completamente diferente do padrao modular do curso (ex: sem src/modules/, sem separacao por modulos), o projeto deve ser reprovado.**

### 2. Analise das Rotas da API
Verifique se os seguintes endpoints estao implementados:

- **POST /products**: Cadastro de produtos.
  - Deve receber dados do produto (ex: name, description, purchasePrice, stock) e retornar o produto criado.

- **POST /clients**: Cadastro de clientes.
  - Deve receber dados do cliente (ex: name, email, document, address) e retornar o cliente criado.

- **POST /checkout**: Realizacao da compra/pedido.
  - Deve receber dados do pedido (ex: clientId, products) e processar o checkout.

- **GET /invoice/:id** (ou **/invoice/{id}**): Consulta de nota fiscal.
  - Deve receber o ID da invoice e retornar os dados da nota fiscal gerada.

### 3. Analise dos Testes E2E
Verifique se existem testes E2E usando **Supertest** que:
- Testam o endpoint **POST /products** (status 201 ou 200 e corpo da resposta).
- Testam o endpoint **POST /clients** (status 201 ou 200 e corpo da resposta).
- Testam o endpoint **POST /checkout** (status 200 ou 201 e corpo da resposta).
- Testam o endpoint **GET /invoice/:id** (status 200 e corpo da resposta).
- Os testes devem validar tanto o status code quanto o corpo da resposta.

### 4. Analise do Framework Web
Verifique se:
- O projeto utiliza **Express** como framework web.
- As rotas estao configuradas corretamente (ex: `app.post('/products', ...)`, `router.get('/invoice/:id', ...)`, etc).

### 5. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- Todos os testes devem passar.
- Se algum teste falhar, inclua os erros relevantes na avaliacao.

### 6. Analise do README.md
Verifique se contem:
- Instrucoes de como instalar dependencias.
- Instrucoes de como rodar os testes.

### 7. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio.
- Todo o codigo deve estar na branch `main`.
- O projeto deve utilizar a estrutura base do monolito modular.

### 8. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Os 4 endpoints estao implementados (POST /products, POST /clients, POST /checkout, GET /invoice/:id).
- Existem testes E2E com Supertest cobrindo os 4 endpoints.
- Os testes validam status code e corpo da resposta.
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O endpoint GET /invoice/:id nao esta implementado' ou 'Nao existem testes E2E para o endpoint POST /checkout']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Implementar a Camada de API (Web) do monolito, criando endpoints para o fluxo completo de uma compra via requisicoes HTTP, com testes E2E.

Tecnologias: TypeScript, Express, Supertest.

Requisitos:
1. POST /products: Cadastro de produtos.
2. POST /clients: Cadastro de clientes.
3. POST /checkout: Realizacao da compra.
4. GET /invoice/:id: Consulta de nota fiscal.
5. Testes E2E com Supertest validando status code e corpo da resposta para todos os endpoints.
6. Comando `npm run test` deve executar todos os testes.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README. Branch `main`.
