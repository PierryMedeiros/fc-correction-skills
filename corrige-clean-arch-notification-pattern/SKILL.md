---
name: corrige-clean-arch-notification-pattern
description: >
  Corrige e avalia o desafio de Notification Pattern na Entidade Product em TypeScript.
  TRIGGER quando: desafio de notification pattern, notification, product, acumulador de erros,
  clean architecture notification, notificacao, erros simultaneos, validacao product,
  TypeScript notification, fc-clean-architecture, multiple errors.
  Palavras-chave: notification pattern, notification, product, acumulador de erros,
  erros simultaneos, validacao, TypeScript, Jest, clean architecture, fc-clean-architecture,
  refatoracao, entidade product, multiple errors, notificacao.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Notification Pattern na Entidade Product

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Clean Architecture: Notification Pattern na Entidade Product".

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
  infrastructure/
    product/
      repository/      (product.repository.ts, product.model.ts)
  usecase/             (pode existir ou nao dependendo do desafio)
```

Verifique tambem:
- Deve existir a entidade `Product` (ex: `product.ts`).
- Deve existir(em) arquivo(s) de teste para a entidade Product.
- `README.md` com instrucoes de como rodar os testes.

**Se a estrutura do repositorio estiver completamente diferente do padrao do curso (ex: tudo em uma pasta so, sem separacao domain/infrastructure, sem @shared), o projeto deve ser reprovado.**

### 2. Analise do Notification Pattern na Entidade Product
Verifique se a entidade Product foi refatorada para usar o Notification Pattern:
- A entidade **nao deve lancar excecoes (throw new Error)** imediatamente ao encontrar um erro de validacao.
- A entidade deve utilizar um **objeto de notificacao** (Notification ou equivalente) para acumular erros.
- Os erros devem ser adicionados a notificacao (ex: `this.notification.addError()`, `this.notification.errors.push()`, ou similar).
- A entidade so deve ser considerada invalida se houver erros na notificacao.

### 3. Analise das Regras de Validacao
Verifique se as regras de negocio da entidade Product continuam sendo verificadas:
- Validacao de **nome** (nao pode ser vazio).
- Validacao de **preco** (deve ser maior ou igual a zero, ou maior que zero conforme o projeto base).
- Outras validacoes existentes no projeto base devem ser mantidas.

### 4. Analise do Teste de Multiplos Erros
Verifique se existe um teste especifico que:
- Forca **dois erros de validacao simultaneos** (ex: Name vazio E Price negativo ao mesmo tempo).
- Verifica se a notificacao contem **ambos os erros** (nao apenas o primeiro).
- Este teste e **obrigatorio** conforme o enunciado.

### 5. Analise dos Testes Existentes
Verifique se:
- Os testes existentes do projeto base continuam presentes e adaptados ao novo padrao.
- Os testes validam que erros sao acumulados na notificacao ao inves de serem lancados como excecoes.

### 6. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- Todos os testes devem passar.
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
- A entidade Product utiliza o Notification Pattern (acumula erros ao inves de lancar excecoes).
- As regras de validacao de nome e preco estao mantidas.
- Existe um teste especifico que forca dois erros simultaneos e verifica ambos na notificacao.
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de como rodar os testes.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'Nao existe um teste que force dois erros de validacao simultaneos' ou 'A entidade Product ainda lanca excecoes ao inves de usar o Notification Pattern']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Refatorar a validacao da entidade Product para utilizar o Notification Pattern. Substituir o lancamento imediato de excecoes por um container acumulador de erros, permitindo que a aplicacao identifique e reporte todas as inconsistencias de uma unica vez.

Tecnologias: TypeScript, Notification Pattern, Jest.

Requisitos Tecnicos:
1. Refatoracao: Modificar a classe Product para utilizar o padrao Notification. Ao inves de lancar Error imediatamente, a entidade deve adicionar o erro a notificacao.
2. Validacao: Todas as regras de negocio atuais da entidade devem continuar sendo verificadas.
3. Teste de Multiplos Erros: Obrigatorio criar um teste que force dois erros simultaneos (ex: Name vazio e Price negativo) e verifique se a notificacao contem ambos os erros.

Entregavel: Repositorio unico no GitHub com codigo refatorado, testes e README com instrucoes de execucao dos testes. Branch `main`. Base obrigatoria: `fc-clean-architecture`.
