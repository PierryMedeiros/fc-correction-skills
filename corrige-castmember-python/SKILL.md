---
name: corrige-castmember-python
description: >
  Corrige e avalia o desafio de API CastMember com Python e Django.
  TRIGGER quando: desafio de CastMember, cast member, membro de elenco, Django, Python,
  catalogo de video, codeflix, catalog admin, API REST Django, CRUD CastMember.
  Palavras-chave: CastMember, cast member, elenco, Django, Python, codeflix, catalogo,
  video, API, REST, CRUD, use case, entidade, dominio, requirements.txt.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - API CastMember com Python e Django

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "API CastMember".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Se houver `docker-compose.yml`, execute `docker compose up -d --build` e teste os endpoints via `curl`.
2. Se for um projeto Django puro, execute `pip install -r requirements.txt` e `python manage.py test` para rodar os testes.
3. Verifique se os endpoints CRUD de CastMember funcionam (POST, GET, PUT/PATCH, DELETE).
4. Ao final, limpe os containers se aplicavel (`docker compose down -v`).
5. Inclua os resultados da execucao na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
Verifique se existem:
- Codigo-fonte Python com Django
- `requirements.txt` com dependencias listadas
- Arquivos de teste
- `README.md`

### 2. Analise da Entidade CastMember
Verifique se a entidade CastMember esta implementada no dominio:
- Deve ter atributos como `id`, `name`, `type` (ACTOR/DIRECTOR).
- Deve ter validacoes (nome obrigatorio, tipo valido).

### 3. Analise dos Casos de Uso
Verifique se os Use Cases estao implementados:
- **CreateCastMember**: Cria um novo membro de elenco.
- **ListCastMember**: Lista membros de elenco.
- **DeleteCastMember**: Remove um membro de elenco.
- **UpdateCastMember**: Atualiza um membro de elenco.

### 4. Analise da API (Endpoints)
Verifique se os endpoints REST estao expostos:
- `POST /cast_members/` - Criar
- `GET /cast_members/` - Listar
- `DELETE /cast_members/{id}/` - Deletar
- `PUT /cast_members/{id}/` ou `PATCH` - Atualizar

### 5. Analise dos Testes
Verifique se existem testes que cubram:
- Testes unitarios da entidade e/ou use cases.
- Testes de integracao/e2e dos endpoints da API.

### 6. Analise do requirements.txt
Verifique se o arquivo existe e contem as dependencias do projeto.

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- A entidade CastMember esta implementada com atributos e validacoes.
- Pelo menos os use cases de Create e List estao implementados.
- Os endpoints da API estao expostos.
- Existem testes automatizados.
- O `requirements.txt` existe e contem dependencias.
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo esta na branch main.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido]"
