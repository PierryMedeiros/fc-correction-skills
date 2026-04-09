---
name: corrige-codeflix-py-patch-api-categoria
description: >
  Corrige e avalia o desafio de Codeflix Python - Implementar API PATCH para Categoria.
  TRIGGER quando: desafio de codeflix python PATCH API, partial_update categoria,
  atualizacao parcial, PATCH categoria, partial=True serializer,
  administracao catalogo video python patch api categoria.
  Palavras-chave: codeflix, catalogo video, python, Django, DRF, PATCH, API,
  partial_update, atualizacao parcial, categoria, category, partial=True,
  serializer, name, description, is_active, testes parciais.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: API PATCH para Categoria

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Implementar API para PATCH".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django/DRF com app de category.
- `requirements.txt` presente.
- Metodo `partial_update` implementado na view.

### 2. Analise da Implementacao do PATCH
- Metodo `partial_update` na view com assinatura `def partial_update(self, request, pk: UUID = None) -> Response`.
- Usa serializer com `partial=True` OU serializer dedicado com todos os campos `required=False`.
- Apenas os campos enviados no payload sao atualizados — os demais permanecem inalterados.

### 3. Analise dos Testes
Testes obrigatorios para atualizacao parcial isolada de cada campo:
- **Apenas name**: Envia so `name`, verifica que `description` e `is_active` permaneceram iguais.
- **Apenas description**: Envia so `description`, verifica que `name` e `is_active` permaneceram iguais.
- **Apenas is_active**: Envia so `is_active`, verifica que `name` e `description` permaneceram iguais.
- Os testes devem **verificar explicitamente** que campos nao enviados ficaram inalterados.

### 4. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
**APROVADO** se:
- Metodo `partial_update` implementado na view.
- Serializer com `partial=True` ou campos `required=False`.
- Testes para atualizacao parcial de cada campo isoladamente (name, description, is_active).
- Testes verificam que campos nao enviados permaneceram inalterados.
- Testes passam.
- `requirements.txt` presente.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
