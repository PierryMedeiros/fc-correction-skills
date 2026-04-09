---
name: corrige-clean-arch-api-product
description: >
  Corrige e avalia o desafio de Clean Architecture - API de Listagem de Products em TypeScript.
  TRIGGER quando: desafio de API de products, API product, endpoint product, GET /product,
  listagem de produtos, clean architecture API, Express product, e2e product,
  fc-clean-architecture API, rota product, route product.
  Palavras-chave: clean architecture, API, product, endpoint, GET, listagem, produtos,
  Express, e2e, Supertest, TypeScript, Jest, fc-clean-architecture,
  rota, route, product.route, product.e2e.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Clean Architecture: API de Listagem de Products

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Clean Architecture: API de Listagem de Produtos".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test`.
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se o projeto utiliza a estrutura base do repositorio `fc-clean-architecture`.
O repositorio do aluno DEVE seguir a organizacao de pastas do curso. Ter arquivos/pastas a mais e aceitavel (desde que faca sentido no contexto de Clean Architecture), mas ter a menos ou de forma desorganizada e motivo de reprovacao.

**Estrutura minima obrigatoria de pastas (baseada no repo oficial do curso):**
```
src/
  domain/
    @shared/
      entity/          (entity.abstract.ts)
      notification/    (notification.ts, notification.error.ts)
      repository/      (repository-interface.ts)
      validator/       (validator.interface.ts)
    customer/
      entity/          (customer.ts)
    product/
      entity/          (product.ts, product.interface.ts)
      factory/         (product.factory.ts)
      repository/      (product-repository.interface.ts)
      service/         (product.service.ts)
  infrastructure/
    api/
      routes/          (product.route.ts ou equivalente)
      __tests__/       (product.e2e.spec.ts ou equivalente)
      express.ts
      server.ts
    product/
      repository/      (product.repository.ts, product.model.ts)
  usecase/
    product/
      list/            (list.product.usecase.ts)
```

Verifique tambem:
- `README.md` com instrucoes de como rodar a API e os testes.

**Se a estrutura do repositorio estiver completamente diferente do padrao do curso (ex: tudo em uma pasta so, sem separacao domain/infrastructure/usecase), o projeto deve ser reprovado.**

### 2. Analise do Endpoint da API
Verifique se existe um endpoint para listar produtos:
- **Rota:** `GET /product` (ou `GET /products` ou equivalente).
- A rota deve chamar o Use Case `ListProduct` (ou equivalente).
- A resposta deve retornar um JSON com a lista de produtos e status code 200.
- O endpoint deve estar registrado nas rotas do Express (ex: `product.route.ts`).

### 3. Analise do Teste E2E
Verifique se existe um teste End-to-End que:
- Simula uma requisicao HTTP real para a rota de listagem (usando Supertest ou similar).
- Valida que o status code retornado e 200.
- Valida que o corpo da resposta contem os dados esperados (lista de produtos em JSON).
- O arquivo de teste pode ser `product.e2e.spec.ts`, `product.e2e-spec.ts`, ou similar.

### 4. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- Todos os testes devem passar.
- Se algum teste falhar, inclua os erros relevantes na avaliacao.

### 5. Analise do README.md
Verifique se contem:
- Instrucoes de como instalar dependencias.
- Instrucoes de como rodar os testes.

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.
- O projeto deve utilizar a estrutura base do repositorio `fc-clean-architecture`.

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O projeto segue a estrutura de pastas do repositorio base `fc-clean-architecture`.
- Existe um endpoint GET para listar produtos (ex: `GET /product`).
- O endpoint chama o Use Case de listagem e retorna JSON com status 200.
- Existe um teste E2E que valida o status code e o corpo da resposta.
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de como rodar os testes.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O endpoint GET /product nao esta implementado' ou 'Nao existe teste E2E para a listagem de produtos']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Implementar a camada de API (Web) para a entidade Product, criando um endpoint de listagem que exponha o Use Case ListProduct via requisicao HTTP, com teste E2E.

Tecnologias: TypeScript, Express, Supertest, Jest.

Requisitos:
1. Endpoint GET /product (ou equivalente) que chama o Use Case ListProduct.
2. Resposta JSON com lista de produtos e status 200.
3. Teste E2E com Supertest validando status code e corpo da resposta.
4. Comando `npm run test` deve executar todos os testes.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README. Branch `main`. Base obrigatoria: `fc-clean-architecture`.
