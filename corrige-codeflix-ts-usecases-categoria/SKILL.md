---
name: corrige-codeflix-ts-usecases-categoria
description: >
  Corrige e avalia o desafio de Codeflix TS - Casos de uso de categoria e cobertura de testes.
  TRIGGER quando: desafio de codeflix use cases categoria, casos de uso categoria,
  cobertura de testes typescript, code coverage 80, tsc check, create update delete
  get search list categoria, administracao catalogo video typescript use cases.
  Palavras-chave: codeflix, catalogo video, typescript, use cases, categoria, category,
  create, update, delete, get, search, list, cobertura de testes, code coverage,
  80 porcento, tsc check, Jest, npm run tsc:check.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix TS: Use Cases de Categoria e Cobertura de Testes

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Cobertura de testes e Casos de uso de categoria".

**MODO DE AVALIACAO: Analise estatica + execucao de testes e verificacao de tipagem.**

Voce DEVE executar os seguintes comandos:
1. `npm install`
2. `npm run tsc:check` — deve retornar sem erros.
3. `npm run test -- --coverage` (ou `npm run test:cov`) — todos os testes devem passar e a cobertura deve ser >= 80%.
4. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Analise dos Use Cases de Categoria
Verifique se os 5 Use Cases estao implementados:
- **Create**: Criacao de nova categoria.
- **Update**: Atualizacao de categoria existente.
- **Delete**: Remocao de categoria.
- **Get**: Recuperacao de categoria especifica.
- **Search/List**: Listagem e busca de categorias.

### 2. Analise da Configuracao de Qualidade
- Jest configurado para falhar se cobertura < 80%.
- Script `tsc:check` no package.json que executa `tsc --noEmit` (ou equivalente).

### 3. Criterios de Aceite (executar)
- `npm run tsc:check` sem erros.
- Todos os testes passam.
- Cobertura >= 80%.

### 4. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
**APROVADO** se:
- Os 5 Use Cases existem (Create, Update, Delete, Get, Search/List).
- `npm run tsc:check` passa sem erros.
- Testes passam com cobertura >= 80%.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
