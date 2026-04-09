---
name: corrige-clean-arch-validacao-product
description: >
  Corrige e avalia o desafio de Validacao Desacoplada na Entidade Product em TypeScript.
  TRIGGER quando: desafio de validacao de products, validacao desacoplada, validator pattern,
  validation factory, ProductYupValidator, yup validator, product validator,
  clean architecture validacao, fc-clean-architecture, desacoplamento validacao.
  Palavras-chave: validacao, validation, product, validator, yup, ProductYupValidator,
  validation factory, desacoplamento, TypeScript, Jest, clean architecture,
  fc-clean-architecture, refatoracao, entidade product, validator pattern.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Validacao Desacoplada na Entidade Product

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Clean Architecture: Validacao Desacoplada na Entidade Product".

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
      entity/          (product.ts, product.interface.ts, product.spec.ts)
      factory/         (product.factory.ts)
      repository/      (product-repository.interface.ts)
      service/         (product.service.ts)
      validator/       (product.yup.validator.ts ou equivalente)
  infrastructure/
    product/
      repository/      (product.repository.ts, product.model.ts)
  usecase/             (pode existir ou nao dependendo do desafio)
```

Verifique tambem:
- Deve existir a entidade `Product` (ex: `product.ts`).
- Deve existir uma classe validadora especifica para Product (ex: `ProductYupValidator`, `product.yup.validator.ts`, ou similar).
- Deve existir(em) arquivo(s) de teste para a entidade Product.
- `README.md` com instrucoes de como rodar os testes.

**Se a estrutura do repositorio estiver completamente diferente do padrao do curso (ex: tudo em uma pasta so, sem separacao domain/infrastructure, sem @shared), o projeto deve ser reprovado.**

### 2. Analise do Validator Desacoplado
Verifique se foi criada uma classe de validacao especifica para Product:
- Deve existir um `ProductYupValidator` (ou equivalente) que implemente uma interface de validacao (ex: `ValidatorInterface`).
- O validator deve utilizar uma biblioteca de validacao (ex: Yup, Zod, class-validator, ou similar) para definir as regras.
- O validator deve preencher o Notification (do desafio anterior) em caso de erros.

### 3. Analise do Desacoplamento na Entidade Product
Verifique se a entidade Product foi refatorada para delegar a validacao:
- A entidade **nao deve conter regras de validacao diretas** (if/else soltos verificando nome, preco, etc).
- A entidade deve **chamar o validador** para realizar a validacao (ex: `this.validate()` que internamente usa o validator).
- Pode existir uma **Validation Factory** que instancia o validador correto para Product.

### 4. Analise da Integridade do Comportamento
Verifique se:
- O comportamento externo da entidade nao mudou (ela continua rejeitando dados invalidos).
- As regras de negocio continuam as mesmas (nome nao vazio, preco valido, etc).
- A mudanca e interna: o "como" foi alterado, mas o "o que" permanece.

### 5. Analise dos Testes (Regressao)
Verifique se:
- Os testes existentes do projeto base continuam presentes.
- Os testes continuam passando (garantia de regressao).
- Como se trata de uma refatoracao, nenhum teste existente deve ter sido removido ou quebrado.

### 6. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- **Todos os testes devem passar.** Como se trata de uma refatoracao, testes falhando indicam que o comportamento externo foi alterado indevidamente.
- Se algum teste falhar, inclua os erros relevantes na avaliacao.

### 7. Analise do README.md
Verifique se o README contem:
- Instrucoes de como rodar os testes.

### 8. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (nao deve ser um monorepo).
- Todo o codigo deve estar na branch `main`.
- O projeto deve utilizar a estrutura base do repositorio `fc-clean-architecture`.

### 9. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O projeto utiliza a estrutura base do repositorio `fc-clean-architecture`.
- Existe uma classe validadora especifica para Product (ex: `ProductYupValidator`).
- A entidade Product delega a validacao ao validador (nao contem regras diretas de if/else).
- O comportamento externo da entidade continua o mesmo (regressao).
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de como rodar os testes.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'Nao existe uma classe validadora especifica para Product' ou 'A entidade Product ainda contem regras de validacao diretas (if/else)' ou 'Os testes falham ao executar npm run test']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Replicar o processo de validacao desacoplada para a entidade Product. Retirar as regras de validacao diretas da entidade e delega-las a uma classe validadora especializada, minimizando o acoplamento no dominio.

Tecnologias: TypeScript, Validator Pattern / Validation Factory, Jest.

Requisitos Tecnicos:
1. Criacao do Validator: Implementar uma classe de validacao especifica para Product (ProductYupValidator), seguindo o padrao de interfaces definido no modulo.
2. Desacoplamento: Refatorar a entidade Product para que nao valide dados diretamente (sem if/else soltos), usando o validador criado. O validador deve preencher o Notification em caso de erros.
3. Integridade: O comportamento externo da entidade nao deve mudar. Ela deve continuar rejeitando dados invalidos, mas internamente o processo e delegado.
4. Testes de Regressao: Todos os testes existentes devem continuar passando.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README com instrucoes de execucao. Branch `main`. Base obrigatoria: `fc-clean-architecture`.
