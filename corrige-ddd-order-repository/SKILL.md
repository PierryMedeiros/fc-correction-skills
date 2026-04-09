---
name: corrige-ddd-order-repository
description: >
  Corrige e avalia o desafio de DDD Patterns - Metodos de OrderRepository.
  TRIGGER quando: desafio de DDD, domain driven design, OrderRepository, order repository,
  fc-ddd-patterns, pedidos, orders, repositorio de pedidos, TypeScript DDD,
  OrderRepositoryInterface, create update find findAll.
  Palavras-chave: DDD, domain driven design, OrderRepository, order, pedido, repository,
  interface, create, update, find, findAll, TypeScript, Sequelize, testes, fc-ddd-patterns.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - DDD OrderRepository

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "DDD: Implementacao de Repository e Testes".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test`.
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
Verifique se o projeto utiliza a estrutura base do repositorio `fc-ddd-patterns`.
O repositorio do aluno DEVE seguir a organizacao de pastas do curso. Ter arquivos/pastas a mais e aceitavel (desde que faca sentido no contexto de DDD), mas ter a menos ou de forma desorganizada e motivo de reprovacao.

**Estrutura minima obrigatoria de pastas (baseada no repo oficial do curso):**
```
src/
  domain/
    @shared/
      event/           (event-dispatcher.ts, interfaces)
      repository/      (repository-interface.ts)
    checkout/
      entity/          (order.ts, order_item.ts)
      factory/         (order.factory.ts)
      repository/      (order-repository.interface.ts)
      service/         (order.service.ts)
    customer/
      entity/          (customer.ts)
      factory/         (customer.factory.ts)
      repository/      (customer-repository.interface.ts)
      value-object/    (address.ts)
    product/
      entity/          (product.ts, product.interface.ts)
      event/           (product-created.event.ts)
      factory/         (product.factory.ts)
      repository/      (product-repository.interface.ts)
      service/         (product.service.ts)
  infrastructure/
    customer/repository/sequelize/  (customer.repository.ts, customer.model.ts)
    order/repository/sequilize/     (order.repository.ts, order.model.ts, order-item.model.ts)
    product/repository/sequelize/   (product.repository.ts, product.model.ts)
```

Verifique tambem:
- Deve existir a classe `OrderRepository` na camada de infraestrutura.
- Deve existir arquivo(s) de teste para o `OrderRepository`.
- `README.md` com instrucoes.

**Se a estrutura do repositorio estiver completamente diferente do padrao do curso (ex: tudo em uma pasta so, sem separacao domain/infrastructure), o projeto deve ser reprovado.**

### 2. Analise da Classe OrderRepository
Verifique se a classe `OrderRepository` implementa completamente a interface `OrderRepositoryInterface`:
- **create**: Persiste um novo pedido (Order) com seus itens (OrderItems) no banco.
- **update**: Atualiza um pedido existente e seus itens.
- **find**: Busca um pedido por ID e retorna a entidade Order completa com seus itens.
- **findAll**: Busca todos os pedidos e retorna uma lista de entidades Order com seus itens.

### 3. Analise dos Testes Automatizados
Verifique se existem testes que validam:
- Criacao de Order (create).
- Atualizacao de Order (update).
- Busca de Order por ID (find).
- Busca de todos os Orders (findAll).
- Os testes devem verificar que os dados sao manipulados corretamente.

### 4. Analise do README.md
Verifique se contem:
- Instrucoes de como instalar dependencias.
- Instrucoes de como rodar os testes.

### Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- A classe `OrderRepository` existe e implementa os metodos `create`, `update`, `find` e `findAll`.
- Os metodos manipulam corretamente a entidade Order e seus OrderItems.
- Existem testes automatizados que cobrem os 4 metodos (create, update, find, findAll).
- O README contem instrucoes basicas.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido]"
