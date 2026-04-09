---
name: corrige-codeflix-ts-repositorio-validacao-categoria
description: >
  Corrige e avalia o desafio de Codeflix TS - Repositorio e validacao da entidade Categoria.
  TRIGGER quando: desafio de codeflix repositorio categoria, validacao categoria,
  class-validator, CategoryInMemoryRepository, in-memory repository,
  filtro por nome, ordenacao created_at, administracao catalogo video typescript repositorio.
  Palavras-chave: codeflix, catalogo video, typescript, repositorio, repository,
  in-memory, CategoryInMemoryRepository, class-validator, validacao, categoria,
  filtro nome, ordenacao created_at, Jest, testes.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix TS: Repositorio e Validacao da Entidade Categoria

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Repositorio e validacao da entidade Categoria".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes:
1. `npm install && npm run test`
2. Inclua o resultado dos testes na avaliacao.

## Procedimento de Avaliacao

### 1. Analise da Validacao com class-validator
- A entidade Categoria deve usar `class-validator` para validacoes.
- Testes unitarios devem validar que dados invalidos sao rejeitados.

### 2. Analise do Repositorio In-Memory
- Deve existir abstracao de repositorio (interface/classe abstrata).
- Deve existir `CategoryInMemoryRepository` (ou equivalente) com testes.

### 3. Regras de Busca e Ordenacao
- **Filtro por nome**: busca por substring (pesquisa textual parcial).
- **Ordenacao padrao**: se nenhum sort for informado, ordenar por `created_at`.

### 4. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
**APROVADO** se:
- Validacao com class-validator implementada na entidade Categoria.
- CategoryInMemoryRepository implementado com testes.
- Filtro por nome (substring) e ordenacao padrao por created_at funcionam.
- Todos os testes passam.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
