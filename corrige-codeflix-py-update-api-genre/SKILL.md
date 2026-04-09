---
name: corrige-codeflix-py-update-api-genre
description: >
  Corrige e avalia o desafio de Codeflix Python - Update API de Genre (PUT).
  TRIGGER quando: desafio de codeflix python update API genre, PUT genre,
  atualizar genero API, update genre view, test_views genre,
  administracao catalogo video python update api genre.
  Palavras-chave: codeflix, catalogo video, python, Django, DRF, update, API,
  genre, genero, PUT, substituicao total, test_when_request_data_is_valid,
  test_when_genre_does_not_exist, categories, views.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: Update API de Genre (PUT)

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Update API".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django/DRF com app de genre (genre_app).
- `requirements.txt` presente.
- Metodo PUT implementado na view de Genre.

### 2. Analise da Implementacao do PUT
- Endpoint PUT para atualizar Genre.
- Comportamento de **substituicao total**: todos os valores do payload substituem o registro existente.
- Se um genero tinha 3 categorias e a atualizacao passa 2, deve ficar com apenas 2.

### 3. Analise dos Testes
Os 4 cenarios obrigatorios devem estar cobertos:
- **test_when_request_data_is_valid_then_update_genre**: Atualizacao com dados validos.
- **test_when_request_data_is_invalid_then_return_400**: Dados invalidos retornam 400.
- **test_when_related_categories_do_not_exist_then_return_400**: Categorias inexistentes retornam 400.
- **test_when_genre_does_not_exist_then_return_404**: Genre inexistente retorna 404.

### 4. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
**APROVADO** se:
- Endpoint PUT implementado com comportamento de substituicao total.
- Os 4 cenarios de teste estao cobertos (nomes podem variar, mas os cenarios devem existir).
- Testes passam.
- `requirements.txt` presente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
