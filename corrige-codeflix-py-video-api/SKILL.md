---
name: corrige-codeflix-py-video-api
description: >
  Corrige e avalia o desafio de Codeflix Python - Video API (CreateVideoWithoutMedia).
  TRIGGER quando: desafio de codeflix python video API, CreateVideoWithoutMedia,
  criar video sem midia, video API Django, testes e2e video,
  administracao catalogo video python video api.
  Palavras-chave: codeflix, catalogo video, python, Django, DRF, video, API,
  CreateVideoWithoutMedia, criar video, sem midia, testes e2e, testes unitarios,
  cenario sucesso, cenario falha, video endpoint.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: Video API (CreateVideoWithoutMedia)

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Video API".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django/DRF com app de video.
- `requirements.txt` presente.
- Camada de API para video (views, serializers, urls).
- Use case `CreateVideoWithoutMedia` implementado.

### 2. Analise da API
- Endpoint para criar video sem midia (POST).
- Camada de API expondo o use case `CreateVideoWithoutMedia`.
- Serializers para validacao de entrada e formatacao de saida.

### 3. Analise dos Testes E2E (minimo 2)
- **Cenario de sucesso**: Video persistido corretamente — verifica status 201 e dados no banco.
- **Cenario de falha**: Erro(s) na requisicao — verifica status 400 e mensagens de erro.

### 4. Analise dos Testes Unitarios
- Testes unitarios para o use case `CreateVideoWithoutMedia`.
- Validacao da logica de negocio isolada (com mocks se necessario).

### 5. Verificacao do requirements.txt
- Todas as dependencias listadas.

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 7. Logica de Aprovacao
**APROVADO** se:
- API para `CreateVideoWithoutMedia` implementada.
- Pelo menos 2 testes E2E (sucesso + falha).
- Testes unitarios para o use case.
- Testes passam (se executados).
- `requirements.txt` presente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
