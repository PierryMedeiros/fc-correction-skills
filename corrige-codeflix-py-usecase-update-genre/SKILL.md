---
name: corrige-codeflix-py-usecase-update-genre
description: >
  Corrige e avalia o desafio de Codeflix Python - Caso de uso Atualizar Genero.
  TRIGGER quando: desafio de codeflix python caso de uso atualizar genero,
  UpdateGenre use case, GenreNotFound, InvalidGenre, RelatedCategoriesNotFound,
  administracao catalogo video python update genre usecase.
  Palavras-chave: codeflix, catalogo video, python, Django, use case, UpdateGenre,
  atualizar genero, GenreNotFound, InvalidGenre, RelatedCategoriesNotFound,
  substituicao total, categorias vinculadas, testes unitarios, integracao.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: Caso de Uso Atualizar Genero

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Caso de uso: Atualizar Genero".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django com app de genre.
- Use case `UpdateGenre` (ou equivalente) implementado.
- `requirements.txt` presente.

### 2. Analise do Use Case UpdateGenre
- Comportamento de **substituicao total** (PUT, nao PATCH).
- Se um genero tinha 3 categorias e a atualizacao passa 2, fica com apenas 2.
- Valida atributos como `name` e `is_active`.

### 3. Analise dos Testes (4 cenarios obrigatorios)
- **Genre nao encontrado**: Tentar atualizar Genre inexistente deve lancar `GenreNotFound` (ou equivalente).
- **Atributos invalidos**: Dados invalidos (ex: nome vazio) devem lancar `InvalidGenre` (ou equivalente).
- **Categorias inexistentes**: Vincular IDs de categorias que nao existem deve lancar `RelatedCategoriesNotFound` (ou equivalente).
- **Happy Path**: Atualizar com dados validos e categorias existentes deve persistir corretamente. Verificar substituicao total das categorias e validacao de name/is_active.

### 4. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
**APROVADO** se:
- Use case UpdateGenre implementado com substituicao total.
- Os 4 cenarios de teste cobertos (GenreNotFound, InvalidGenre, RelatedCategoriesNotFound, Happy Path).
- Testes passam.
- `requirements.txt` presente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
