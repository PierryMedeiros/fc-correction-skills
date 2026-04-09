---
name: corrige-ddd-customer-events
description: >
  Corrige e avalia o desafio de DDD Patterns - Eventos de Customer.
  TRIGGER quando: desafio de DDD eventos, domain events, customer events,
  CustomerCreated, CustomerAddressChanged, event handler, domain event handler,
  EnviaConsoleLog, EventDispatcher, customer created event, address changed,
  fc-ddd-patterns eventos, TypeScript DDD events.
  Palavras-chave: DDD, domain events, customer, CustomerCreated, CustomerAddressChanged,
  event handler, EventDispatcher, EnviaConsoleLog, console.log, TypeScript,
  testes, fc-ddd-patterns, domain driven design, eventos de dominio.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - DDD Domain Events de Customer

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "DDD: Eventos de Customer".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test`.
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se o projeto utiliza a estrutura base do repositorio `fc-ddd-patterns`.
O repositorio do aluno DEVE seguir a organizacao de pastas do curso. Ter arquivos/pastas a mais e aceitavel (desde que faca sentido no contexto de DDD), mas ter a menos ou de forma desorganizada e motivo de reprovacao.

**Estrutura minima obrigatoria de pastas (baseada no repo oficial do curso):**
```
src/
  domain/
    @shared/
      event/           (event-dispatcher.ts, event-dispatcher.interface.ts, event.interface.ts, event-handler.interface.ts)
      repository/      (repository-interface.ts)
    customer/
      entity/          (customer.ts)
      event/           (customer-created.event.ts, customer-address-changed.event.ts ou similares)
      event/handler/   (send-console-log1.handler.ts, send-console-log2.handler.ts, send-console-log-handler.ts ou similares)
      factory/         (customer.factory.ts)
      repository/      (customer-repository.interface.ts)
      value-object/    (address.ts)
    product/
      entity/          (product.ts)
  infrastructure/
    customer/repository/sequelize/
    product/repository/sequelize/
```

**Se a estrutura do repositorio estiver completamente diferente do padrao do curso (ex: tudo em uma pasta so, sem separacao domain/infrastructure, sem @shared), o projeto deve ser reprovado.**

Verifique especificamente:
- Deve existir a entidade `Customer` (ex: `customer.ts`).
- Devem existir os eventos de dominio:
  - `CustomerCreatedEvent` (ex: `customer-created.event.ts` ou similar).
  - `CustomerAddressChangedEvent` (ex: `customer-address-changed.event.ts`, `address-changed.event.ts`, ou similar).
- Devem existir os handlers:
  - `EnviaConsoleLog1Handler` (para CustomerCreated).
  - `EnviaConsoleLog2Handler` (para CustomerCreated).
  - `EnviaConsoleLogHandler` (para CustomerAddressChanged).
- Devem existir arquivo(s) de teste que validem os eventos e handlers.
- `README.md` com instrucoes de como rodar os testes.

### 2. Analise do Evento CustomerCreated
Verifique se:
- Existe uma classe/tipo de evento `CustomerCreatedEvent` (ou nome equivalente).
- O evento e disparado quando um novo Customer e criado.
- Existem **dois handlers** registrados para este evento:
  - **Handler 1 (EnviaConsoleLog1Handler):** Deve imprimir: `"Esse é o primeiro console.log do evento: CustomerCreated"` (ou mensagem equivalente com mesmo sentido).
  - **Handler 2 (EnviaConsoleLog2Handler):** Deve imprimir: `"Esse é o segundo console.log do evento: CustomerCreated"` (ou mensagem equivalente com mesmo sentido).

### 3. Analise do Evento CustomerAddressChanged
Verifique se:
- Existe uma classe/tipo de evento `CustomerAddressChangedEvent` (ou nome equivalente como `AddressChangedEvent`).
- O evento e disparado quando o endereco do Customer e alterado.
- O evento transporta os dados: **id**, **nome** e **novo endereco** do cliente.
- Existe um handler (`EnviaConsoleLogHandler` ou nome equivalente) que imprime: `"Endereço do cliente: {id}, {nome} alterado para: {endereco}"` (ou mensagem equivalente contendo id, nome e endereco).

### 4. Analise do EventDispatcher
Verifique se:
- Existe um `EventDispatcher` (ou mecanismo equivalente) que gerencia o registro de handlers e o disparo de eventos.
- Os handlers sao registrados no dispatcher para os eventos corretos.

### 5. Analise dos Testes Automatizados
Verifique se existem testes que validam:
- O disparo do evento `CustomerCreatedEvent` e a execucao dos dois handlers.
- O disparo do evento `CustomerAddressChangedEvent` e a execucao do handler com os dados corretos.
- Os testes devem verificar que os handlers sao chamados (ex: usando `spyOn` em `console.log` ou verificando chamadas dos handlers).

### 6. Execucao dos Testes
Execute `npm install && npm run test` no diretorio do projeto:
- Todos os testes devem passar.
- Se algum teste falhar, inclua os erros relevantes na avaliacao.

### 7. Analise do README.md
Verifique se contem:
- Instrucoes de como instalar dependencias.
- Instrucoes de como rodar os testes.

### 8. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio.
- Todo o codigo deve estar na branch `main`.
- O projeto deve utilizar a estrutura base do repositorio `fc-ddd-patterns`.

### 9. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Os eventos `CustomerCreatedEvent` e `CustomerAddressChangedEvent` estao implementados.
- Existem dois handlers para `CustomerCreated` (EnviaConsoleLog1 e EnviaConsoleLog2) com as mensagens corretas.
- Existe um handler para `CustomerAddressChanged` que imprime id, nome e endereco.
- Os eventos sao disparados nos momentos corretos (criacao e troca de endereco).
- Existem testes automatizados que validam o disparo dos eventos e execucao dos handlers.
- Todos os testes passam ao executar `npm run test`.
- O README contem instrucoes de como rodar os testes.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O evento CustomerAddressChangedEvent nao esta implementado' ou 'Nao existem testes para o evento CustomerCreated']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Implementar Domain Events para o agregado Customer. Dois eventos devem ser criados: CustomerCreated (com dois handlers de log) e CustomerAddressChanged (com um handler que imprime id, nome e endereco).

Tecnologias: TypeScript, Domain Events (DDD), Testes Unitarios.

Requisitos:
1. Evento CustomerCreated: Disparado na criacao de Customer. Dois handlers:
   - EnviaConsoleLog1Handler: "Esse é o primeiro console.log do evento: CustomerCreated"
   - EnviaConsoleLog2Handler: "Esse é o segundo console.log do evento: CustomerCreated"
2. Evento CustomerAddressChanged: Disparado na troca de endereco. Transporta id, nome e endereco. Um handler:
   - EnviaConsoleLogHandler: "Endereço do cliente: {id}, {nome} alterado para: {endereco}"
3. Testes unitarios cobrindo disparo de eventos e execucao de handlers.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README. Branch `main`.
