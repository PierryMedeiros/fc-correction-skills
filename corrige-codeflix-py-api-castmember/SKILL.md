---
name: corrige-codeflix-py-api-castmember
description: >
  Corrige e avalia o desafio de Codeflix Python - API CastMember com Django.
  TRIGGER quando: desafio de codeflix python API CastMember, cast member Django,
  membro de elenco python, CastMember entidade use cases API,
  administracao catalogo video python castmember, ator diretor python.
  Palavras-chave: codeflix, catalogo video, python, Django, DRF, CastMember,
  cast member, membro de elenco, ator, diretor, entidade, use cases, API,
  CRUD, endpoints, testes, requirements.txt.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: API CastMember

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "API CastMember".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django/DRF com app de cast_member (ou cast_member_app).
- `requirements.txt` presente.
- Entidade CastMember, Use Cases e camada de API.

### 2. Analise da Entidade CastMember
- Campos: `name` (string), `type` (enum/choice: ACTOR/DIRECTOR ou 1/2), `created_at`.
- Validacoes de dominio (nome obrigatorio, tipo valido).

### 3. Analise dos Use Cases
- **Create**: Criar um CastMember.
- **List**: Listar CastMembers.
- **Get/Find**: Buscar CastMember por ID.
- **Update**: Atualizar CastMember.
- **Delete**: Remover CastMember.

### 4. Analise da API (Endpoints)
- Endpoints REST expostos para as operacoes CRUD.
- Serializers para validacao de entrada e formatacao de saida.
- URLs configuradas corretamente.

### 5. Analise dos Testes
- Testes cobrindo os use cases e/ou endpoints.
- Testes de validacao (dados invalidos).
- Testes de fluxo completo (criar, listar, buscar, atualizar, deletar).

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 7. Logica de Aprovacao
**APROVADO** se:
- Entidade CastMember implementada com campos e validacoes.
- Use Cases CRUD implementados.
- Endpoints da API expostos e funcionais.
- Testes automatizados presentes e passando.
- `requirements.txt` presente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
