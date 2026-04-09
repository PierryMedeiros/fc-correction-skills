---
name: corrige-codeflix-py-paginacao-refatoracao
description: >
  Corrige e avalia o desafio de Codeflix Python - Paginacao e Refatoracao.
  TRIGGER quando: desafio de codeflix python paginacao, paginacao refatoracao,
  DRF pagination, abstracao listagem, duplicacao codigo,
  administracao catalogo video python paginacao refatoracao.
  Palavras-chave: codeflix, catalogo video, python, Django, DRF, paginacao,
  pagination, refatoracao, abstracao, listagem, duplicacao, application layer,
  API layer, views, serializers, Genre, CastMember, Video.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: Paginacao e Refatoracao

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Paginacao e Refatoracao".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django/DRF com apps de dominio (category, genre, cast_member, video).
- `requirements.txt` presente.

### 2. Analise da Paginacao
Verifique se a paginacao esta implementada para **todos os dominios** (alem de Category que ja existia):
- **Genre**: Listagem paginada.
- **CastMember**: Listagem paginada.
- **Video**: Listagem paginada.
- A paginacao deve funcionar corretamente (page, page_size, next, previous, total).

### 3. Analise da Refatoracao/Abstracao
Verifique se o aluno reduziu duplicacao de codigo:
- **Camada de Aplicacao**: Use case de listagem abstrato/generico que pode ser reutilizado entre dominios.
- **Camada de API**: Views e/ou Serializers abstratos que reduzem duplicacao entre os endpoints de listagem.
- A abstracao deve ser real (classes base, mixins, generics) — nao apenas copiar e colar.

### 4. Analise dos Testes
- Testes para paginacao de cada dominio.
- Testes verificando que a refatoracao nao quebrou funcionalidades existentes.

### 5. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 6. Logica de Aprovacao
**APROVADO** se:
- Paginacao implementada para Genre, CastMember e Video (alem de Category).
- Refatoracao com abstracao real na camada de aplicacao e/ou API (nao apenas codigo duplicado).
- Testes passam.
- `requirements.txt` presente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
