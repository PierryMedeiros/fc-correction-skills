---
name: corrige-monolito-modulo-invoice
description: >
  Corrige e avalia o desafio de Sistemas Monoliticos - Modulo de Invoice (Nota Fiscal).
  TRIGGER quando: desafio de monolito invoice, modulo invoice, nota fiscal, faturamento,
  GenerateInvoice, FindInvoice, InvoiceItems, invoice facade, invoice factory,
  invoice repository, invoice use case, fc-monolito invoice, sistemas monoliticos invoice.
  Palavras-chave: monolito, monolitico, invoice, nota fiscal, faturamento, GenerateInvoice,
  FindInvoice, InvoiceItems, facade, factory, repository, use case, TypeScript,
  Jest, fc-monolito, sistemas monoliticos, modulo invoice, generate, find.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Sistemas Monoliticos: Modulo de Invoice

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Sistemas Monoliticos: Criacao do Modulo de Invoice".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test`.
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se o projeto utiliza a estrutura base do repositorio `fc-monolito`.
O repositorio do aluno DEVE seguir a organizacao modular do curso. Ter arquivos/pastas a mais e aceitavel (desde que faca sentido), mas ter a menos ou de forma desorganizada e motivo de reprovacao.

**Estrutura base do monolito (modulos existentes no repo oficial do curso):**
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
```

**Estrutura esperada do modulo Invoice (adicionado pelo aluno em `src/modules/invoice/`):**
```
invoice/
  domain/        (entidades Invoice, InvoiceItems, value object Address)
  facade/        (InvoiceFacade + spec)
  factory/       (InvoiceFacadeFactory)
  gateway/       (InvoiceGateway interface)
  repository/    (InvoiceRepository + spec)
  usecase/
    find-invoice/    (FindInvoiceUseCase + DTO + spec)
    generate-invoice/ (GenerateInvoiceUseCase + DTO + spec)
```

Ter arquivos/pastas a mais e aceitavel. Ter a menos ou desorganizado (ex: tudo em uma pasta so) e motivo de reprovacao.

**Se a estrutura do repositorio estiver completamente diferente do padrao modular do curso (ex: sem src/modules/, sem separacao por modulos), o projeto deve ser reprovado.**

Verifique tambem:
- `README.md` com instrucoes de como rodar os testes.

### 2. Analise da Entidade Invoice (Domain)
Verifique se a entidade Invoice contem:
- **id**: identificador unico.
- **name**: nome do cliente.
- **document**: documento do cliente.
- **address**: Value Object com campos de endereco (street, number, complement, city, state, zipCode).
- **items**: lista de InvoiceItems (cada item com id, name, price).
- **createdAt** e **updatedAt**: timestamps.
- **total**: deve ser calculado (soma dos precos dos items).

### 3. Analise da Entidade InvoiceItems
Verifique se existe uma entidade InvoiceItems com:
- **id**: identificador unico.
- **name**: nome do item.
- **price**: preco do item.

### 4. Analise do Value Object Address
Verifique se existe um Value Object Address com os campos:
- street, number, complement, city, state, zipCode.

### 5. Analise dos Use Cases
Verifique se os 2 Use Cases estao implementados:

**GenerateInvoiceUseCase:**
- Recebe os dados via DTO de input (name, document, endereco, items).
- Cria a entidade Invoice e persiste via gateway/repository.
- Retorna o DTO de output com id, dados do cliente, endereco, items e total.

**FindInvoiceUseCase:**
- Recebe o id via DTO de input.
- Busca a invoice no gateway/repository.
- Retorna o DTO de output com todos os dados da invoice incluindo total e createdAt.

### 6. Analise dos DTOs
Verifique se os DTOs seguem os contratos especificados no enunciado:
- FindInvoiceUseCaseInputDTO com campo `id`.
- FindInvoiceUseCaseOutputDTO com campos id, name, document, address (objeto), items (array), total, createdAt.
- GenerateInvoiceUseCaseInputDto com campos name, document, street, number, complement, city, state, zipCode, items.
- GenerateInvoiceUseCaseOutputDto com campos id, name, document, street, number, complement, city, state, zipCode, items, total.

### 7. Analise da Facade
Verifique se existe uma InvoiceFacade que:
- Expoe os metodos `generate` e `find` (ou equivalentes).
- Serve como interface publica do modulo para comunicacao com outros modulos.

### 8. Analise da Factory
Verifique se existe uma InvoiceFacadeFactory que:
- Instancia o repository, os use cases e a facade.
- Retorna a facade pronta para uso.

### 9. Analise do Repository/Gateway
Verifique se existe:
- Uma interface de gateway (InvoiceGateway) definindo os metodos de persistencia.
- Uma implementacao do repository que persiste e busca invoices.

### 10. Analise dos Testes
Verifique se existem testes que validam:
- O funcionamento do GenerateInvoiceUseCase (criacao de invoice).
- O funcionamento do FindInvoiceUseCase (busca de invoice).
- A integracao com a Facade.
- O repository (persistencia e busca).

### 11. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- Todos os testes devem passar.
- Se algum teste falhar, inclua os erros relevantes na avaliacao.

### 12. Analise do README.md
Verifique se contem:
- Instrucoes de como instalar dependencias.
- Instrucoes de como rodar os testes.

### 13. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.
- O projeto deve utilizar a estrutura base do monolito modular do curso.

### 14. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- A entidade Invoice existe com os campos obrigatorios (id, name, document, address, items, createdAt, updatedAt).
- A entidade InvoiceItems existe com os campos obrigatorios (id, name, price).
- O Value Object Address existe com os campos de endereco.
- O GenerateInvoiceUseCase esta implementado e segue o contrato de DTOs.
- O FindInvoiceUseCase esta implementado e segue o contrato de DTOs.
- A Facade expoe os metodos generate e find.
- A Factory cria a Facade corretamente.
- O Repository/Gateway esta implementado.
- Existem testes automatizados cobrindo os use cases e/ou a facade.
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de como rodar os testes.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O FindInvoiceUseCase nao esta implementado' ou 'A entidade InvoiceItems nao contem o campo price' ou 'A Facade nao expoe o metodo generate']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Implementar o Modulo de Invoice (Nota Fiscal) completo dentro do sistema monolitico, com Domain, Use Cases, Repository, Facade e Factory.

Tecnologias: TypeScript, Modular Monolith, Jest.

Requisitos:
1. Domain: Entidade Invoice (id, name, document, address, items, createdAt, updatedAt), entidade InvoiceItems (id, name, price), Value Object Address.
2. Use Cases: GenerateInvoiceUseCase (criar nota fiscal) e FindInvoiceUseCase (buscar nota fiscal), ambos com DTOs especificos.
3. Repository/Gateway: Interface de gateway e implementacao de persistencia.
4. Facade: Interface publica do modulo com metodos generate e find.
5. Factory: Fabrica que instancia repository, use cases e facade.
6. Testes: Cobertura automatizada dos use cases e facade.
7. Comando `npm run test` deve executar todos os testes.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README. Branch `main`. Base obrigatoria do monolito modular do curso.