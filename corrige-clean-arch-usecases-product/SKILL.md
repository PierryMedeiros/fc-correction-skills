---
name: corrige-clean-arch-usecases-product
description: >
  Corrige e avalia o desafio de Clean Architecture - Use Cases para Product em TypeScript.
  TRIGGER quando: desafio de use cases product, use case product, CRUD product,
  create product, find product, list product, update product, clean architecture use cases,
  fc-clean-architecture, testes unitarios e integracao product, DTO product.
  Palavras-chave: clean architecture, use cases, product, create, find, list, update,
  CRUD, DTO, testes unitarios, testes integracao, TypeScript, Jest,
  fc-clean-architecture, usecase product.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Clean Architecture: Use Cases para Product

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Clean Architecture: Use Cases para a Entidade Product".

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
    product/
      repository/      (product.repository.ts, product.model.ts)
  usecase/
    product/
      create/          (create.product.usecase.ts, create.product.dto.ts)
      find/            (find.product.usecase.ts, find.product.dto.ts)
      list/            (list.product.usecase.ts, list.product.dto.ts)
      update/          (update.product.usecase.ts, update.product.dto.ts)
```

Verifique tambem:
- `README.md` com instrucoes de como rodar os testes.

**Se a estrutura do repositorio estiver completamente diferente do padrao do curso (ex: tudo em uma pasta so, sem separacao domain/infrastructure/usecase), o projeto deve ser reprovado.**

### 2. Analise dos Use Cases
Verifique se os 4 Use Cases para Product estao implementados:

- **CreateProductUseCase** (ou equivalente): Recebe dados via DTO, cria e persiste um produto.
- **FindProductUseCase** (ou equivalente): Busca um produto por ID e retorna via DTO.
- **ListProductUseCase** (ou equivalente): Lista todos os produtos e retorna via DTO.
- **UpdateProductUseCase** (ou equivalente): Atualiza os dados de um produto existente.

Cada Use Case deve:
- Utilizar DTOs de Input e Output para isolar a logica.
- Interagir com o repositorio via interface (nao diretamente com a implementacao).

### 3. Analise dos Testes de Unidade
Verifique se existem testes de **unidade** (com mocks) para CADA um dos 4 Use Cases:
- `create.product.unit.spec.ts` (ou equivalente)
- `find.product.unit.spec.ts` (ou equivalente)
- `list.product.unit.spec.ts` (ou equivalente)
- `update.product.unit.spec.ts` (ou equivalente)

Os testes de unidade devem usar mocks para o repositorio, validando a logica de negocio isolada.

### 4. Analise dos Testes de Integracao
Verifique se existem testes de **integracao** (com banco de dados real) para CADA um dos 4 Use Cases:
- `create.product.integration.spec.ts` (ou equivalente)
- `find.product.integration.spec.ts` (ou equivalente)
- `list.product.integration.spec.ts` (ou equivalente)
- `update.product.integration.spec.ts` (ou equivalente)

Os testes de integracao devem testar o fluxo completo com o banco de dados (Sequelize/SQLite ou similar).

### 5. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- Todos os testes devem passar.
- Se algum teste falhar, inclua os erros relevantes na avaliacao.

### 6. Analise do README.md
Verifique se contem:
- Instrucoes de como instalar dependencias.
- Instrucoes de como rodar os testes.

### 7. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.
- O projeto deve utilizar a estrutura base do repositorio `fc-clean-architecture`.

### 8. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O projeto segue a estrutura de pastas do repositorio base `fc-clean-architecture`.
- Os 4 Use Cases (Create, Find, List, Update) estao implementados para Product.
- Os Use Cases utilizam DTOs de Input/Output.
- Existem testes de unidade (com mocks) para os 4 Use Cases.
- Existem testes de integracao (com banco) para os 4 Use Cases.
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de como rodar os testes.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'Nao existem testes de integracao para o UseCase UpdateProduct' ou 'O UseCase ListProduct nao foi implementado']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Implementar os 4 Use Cases (Create, Find, List, Update) para a entidade Product, seguindo o padrao demonstrado para Customer. Cobertura total de testes: unidade (com mocks) e integracao (com banco) para cada Use Case.

Tecnologias: TypeScript, Clean Architecture, Jest.

Requisitos:
1. 4 Use Cases: CreateProduct, FindProduct, ListProduct, UpdateProduct.
2. DTOs de Input/Output para cada Use Case.
3. Testes de unidade com mocks para os 4 Use Cases.
4. Testes de integracao com banco para os 4 Use Cases.
5. Comando `npm run test` deve executar todos os testes.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README. Branch `main`. Base obrigatoria: `fc-clean-architecture`.
