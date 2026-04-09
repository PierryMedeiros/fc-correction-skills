---
name: corrige-codeflix-ts-endpoints-categoria-castmember
description: >
  Corrige e avalia o desafio de Codeflix TS - Endpoints de Categoria e Cast Member.
  TRIGGER quando: desafio de codeflix endpoints categoria cast member, CRUD cast member,
  CastMember diretor ator, type 1 diretor type 2 ator, endpoints categoria castmember,
  administracao catalogo video typescript endpoints, piramide de testes.
  Palavras-chave: codeflix, catalogo video, typescript, endpoints, categoria, cast member,
  CastMember, diretor, ator, CRUD, API, class-validator, cobertura 80, tsc check,
  piramide de testes, unitarios integracao e2e, Jest.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix TS: Endpoints de Categoria e Cast Member

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Endpoints de Categoria e Cast Member".

**MODO DE AVALIACAO: Analise estatica + execucao de testes e verificacao de tipagem.**

Voce DEVE executar os seguintes comandos:
1. `npm install`
2. `npm run tsc:check` — deve retornar sem erros.
3. `npm run test:cov` (ou `npm run test -- --coverage`) — cobertura >= 80%.
4. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Analise da Entidade CastMember
- Campos: `name` (string, obrigatorio, max 255), `type` (Value Object ou Enum: 1=Diretor, 2=Ator), `created_at`.
- Validacoes de dominio implementadas.

### 2. Analise dos Endpoints CRUD de CastMember
- Create, Update, Get, Delete de Cast Members.
- Listagem com ordenacao por `name` ou `created_at`.
- Listagem com filtro por `name` ou `type`.

### 3. Analise dos Endpoints de Categoria
- CRUD completo de Categoria (deve estar mantido dos desafios anteriores).

### 4. Piramide de Testes
- Testes unitarios, de integracao e E2E presentes.

### 5. Criterios de Aceite (executar)
- `npm run tsc:check` sem erros.
- `npm run test:cov` com cobertura >= 80%.

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 7. Logica de Aprovacao
**APROVADO** se:
- Entidade CastMember com campos e validacoes corretas (name, type 1/2, created_at).
- Endpoints CRUD de CastMember e Categoria implementados.
- Listagem com filtro e ordenacao para CastMember.
- `npm run tsc:check` sem erros.
- Cobertura >= 80%.
- Testes passam.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
