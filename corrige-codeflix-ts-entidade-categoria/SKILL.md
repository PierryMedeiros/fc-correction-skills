---
name: corrige-codeflix-ts-entidade-categoria
description: >
  Corrige e avalia o desafio de Codeflix TS - Criando projeto e entidade Categoria.
  TRIGGER quando: desafio de codeflix typescript, entidade categoria, entity categoria,
  administracao catalogo video typescript, criando projeto entidade categoria,
  DDD entity value object, categoria TypeScript Jest Docker.
  Palavras-chave: codeflix, catalogo video, typescript, categoria, category, entity,
  value object, DDD, Jest, Docker, docker compose, testes unitarios,
  criando projeto, entidade categoria, administracao catalogo.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix TS: Criando Projeto e Entidade Categoria

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Criando projeto e entidade Categoria".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

Alem de ler os arquivos, voce DEVE executar os testes do projeto:
1. Acesse o diretorio do projeto e execute `npm install && npm run test` (ou `docker compose up` se necessario para rodar testes).
2. Inclua o resultado dos testes na sua avaliacao.
3. Se os testes falharem, inclua os erros relevantes no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto TypeScript configurado (tsconfig.json, package.json).
- Docker e Docker Compose configurados (Dockerfile, docker-compose.yml).
- Jest configurado para testes.
- Codigo-fonte com estrutura DDD (ex: `src/` com separacao de camadas).

### 2. Analise das Abstracoes Base
- Deve existir uma classe/abstração base para **Entity**.
- Deve existir uma classe/abstracao base para **Value Object**.

### 3. Analise da Entidade Categoria
- Entidade Categoria deve estender a classe base de Entity.
- Deve ter atributos relevantes (ex: name, description, is_active, created_at).
- Deve ter metodos de negocio e validacoes implementadas dentro da entidade.

### 4. Analise dos Testes
- Testes unitarios com Jest validando: criacao da entidade, validacoes dos atributos, operacoes de negocio.

### 5. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 6. Logica de Aprovacao
**APROVADO** se:
- Projeto TypeScript + Docker + Jest configurados.
- Abstracoes base de Entity e Value Object existem.
- Entidade Categoria implementada com validacoes e metodos de negocio.
- Testes unitarios passam com sucesso.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
