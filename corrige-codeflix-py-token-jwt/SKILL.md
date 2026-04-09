---
name: corrige-codeflix-py-token-jwt
description: >
  Corrige e avalia o desafio de Codeflix Python - Gerando token JWT para testes.
  TRIGGER quando: desafio de codeflix python JWT, token JWT testes, PyJWT RS256,
  Keycloak realm_access roles, chave RSA, gerando token JWT,
  administracao catalogo video python JWT, permission_classes.
  Palavras-chave: codeflix, catalogo video, python, Django, JWT, PyJWT, RS256,
  Keycloak, realm_access, roles, RSA, chave privada, chave publica,
  token, autenticacao, testes integracao, permission_classes.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Codeflix Python: Gerando Token JWT para Testes

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Gerando token JWT para Testes".

**MODO DE AVALIACAO: Analise estatica + execucao de testes.**

1. Execute `pip install -r requirements.txt && python manage.py test` (ou `pytest`) se possivel.
2. Caso contrario, faca analise estatica completa.
3. Inclua os resultados na avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura
- Projeto Django/DRF.
- `requirements.txt` com `PyJWT` (ou equivalente) e dependencias de criptografia.
- Codigo de geracao de token JWT.
- Testes que utilizam o token gerado.

### 2. Analise da Geracao do Token
- Deve usar algoritmo **RS256** (nao HS256).
- Deve usar par de chaves RSA (privada para assinar, publica para verificar).
- As chaves devem ser acessadas via **variaveis de ambiente** (nao hardcoded no codigo de producao).

### 3. Analise do Payload do Token
O payload deve conter a estrutura do Keycloak:
```json
{
  "realm_access": {
    "roles": ["offline_access", "admin", "uma_authorization", "default-roles-codeflix"]
  }
}
```
- A role `admin` deve estar presente.
- A estrutura `realm_access.roles` deve ser respeitada.

### 4. Analise dos Testes
- Testes de integracao devem usar o token gerado para autenticar requisicoes.
- Os testes devem validar permissoes reais (sem mockar `permission_classes`).

### 5. Verificacao do requirements.txt
- `PyJWT` presente.
- Biblioteca de criptografia (ex: `cryptography`) se necessaria para RS256.

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 7. Logica de Aprovacao
**APROVADO** se:
- Token JWT gerado com RS256 e par de chaves RSA.
- Payload replica a estrutura do Keycloak com `realm_access.roles`.
- Chaves acessadas via variaveis de ambiente.
- Testes utilizam o token para autenticar requisicoes sem mockar permissoes.
- `requirements.txt` presente com PyJWT.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado:** "Seu projeto foi aprovado"
- **Se nao aprovado:** "Seu projeto nao foi aprovado pelo seguinte motivo: [motivo especifico]"
