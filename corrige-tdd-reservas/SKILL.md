---
name: corrige-tdd-reservas
description: >
  Corrige e avalia o desafio de TDD - Test Driven Development no sistema de reservas.
  TRIGGER quando: desafio de TDD, test driven development, testes unitarios, testes e2e,
  sistema de reservas, property, booking, guest, refund, cancelamento, mapper,
  property_mapper, booking_mapper, RefundRuleFactory, booking_service, TypeScript, Jest.
  Palavras-chave: TDD, test driven development, reservas, property, booking, guest, user,
  mapper, refund, cancelamento, e2e, unitario, Jest, TypeScript, fc4-tdd.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - TDD no Sistema de Reservas

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Desenvolvimento Orientado a Testes (TDD)".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test`.
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos de Teste
Verifique se os seguintes arquivos de teste existem e nao estao vazios:
- `src/infrastructure/persistence/mappers/property_mapper.test.ts`
- `src/infrastructure/persistence/mappers/booking_mapper.test.ts`
- `src/infrastructure/web/user_controller_e2e.test.ts`
- `src/infrastructure/web/property_controller_e2e.test.ts`
- `src/domain/cancelation/refund_rule_factory.test.ts`
- `src/application/services/booking_service.test.ts` (ja existente, deve conter novo teste)

### 2. Analise dos Testes de Mappers (property_mapper.test.ts)
Verifique se contem os 3 testes:
- "deve converter PropertyEntity em Property corretamente"
- "deve lancar erro de validacao ao faltar campos obrigatorios no PropertyEntity"
- "deve converter Property para PropertyEntity corretamente"

### 3. Analise dos Testes de Mappers (booking_mapper.test.ts)
Verifique se contem os 3 testes:
- "deve converter BookingEntity em Booking corretamente"
- "deve lancar erro de validacao ao faltar campos obrigatorios no BookingEntity"
- "deve converter Booking para BookingEntity corretamente"

### 4. Analise dos Testes E2E de Usuario (user_controller_e2e.test.ts)
Verifique se contem os 2 testes:
- "deve criar um usuario com sucesso"
- "deve retornar erro com codigo 400 e mensagem 'O campo nome e obrigatorio.' ao enviar um nome vazio"

### 5. Analise dos Testes E2E de Propriedade (property_controller_e2e.test.ts)
Verifique se contem os 4 testes:
- "deve criar uma propriedade com sucesso"
- "deve retornar erro com codigo 400 e mensagem 'O nome da propriedade e obrigatorio.' ao enviar um nome vazio"
- "deve retornar erro com codigo 400 e mensagem 'A capacidade maxima deve ser maior que zero.' ao enviar maxGuests igual a zero ou negativo"
- "deve retornar erro com codigo 400 e mensagem 'O preco base por noite e obrigatorio.' ao enviar basePricePerNight ausente"

### 6. Analise dos Testes de RefundRuleFactory (refund_rule_factory.test.ts)
Verifique se contem os 3 testes:
- "deve retornar FullRefund quando a reserva for cancelada com mais de 7 dias de antecedencia"
- "deve retornar PartialRefund quando a reserva for cancelada entre 1 e 7 dias de antecedencia"
- "deve retornar NoRefund quando a reserva for cancelada com menos de 1 dia de antecedencia"

### 7. Analise do Teste de Cancelamento (booking_service.test.ts)
Verifique se contem o teste adicional:
- "deve retornar erro ao tentar cancelar uma reserva que nao existe"

### 8. Analise de Implementacoes
Verifique se foram implementados:
- Metodo `createUser` em `src/application/services/user_service.ts`
- Metodo `createProperty` em `src/application/services/property_service.ts`
- Validacao de `basePricePerNight > 0` em `src/domain/entities/property.ts`

### 9. Analise do README.md
Verifique se contem instrucoes de como instalar dependencias e rodar os testes.

### Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 10. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Todos os 6 arquivos de teste existem e nao estao vazios.
- Os testes especificados estao implementados (podem ter nomes ligeiramente diferentes mas devem cobrir os mesmos cenarios).
- As implementacoes de `createUser`, `createProperty` e validacao de `basePricePerNight` existem.
- O README contem instrucoes basicas.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido]"
