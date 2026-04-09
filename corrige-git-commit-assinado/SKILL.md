---
name: corrige-git-commit-assinado
description: >
  Corrige e avalia o desafio de Git - Assine seu Commit com GPG.
  TRIGGER quando: desafio de git, assine seu commit, commit assinado, GPG,
  verified, assinatura de commit, chave GPG, badge verified, git commit sign,
  assinatura digital, commit verificado.
  Palavras-chave: git, commit assinado, GPG, verified, assinatura, chave GPG,
  badge verified, sign commit, assinatura digital, github verified.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Assinatura de Commits com GPG

Voce e um engenheiro de software experiente. Sua tarefa e avaliar se o aluno cumpriu o desafio "Assinatura de Commits com GPG".

**MODO DE AVALIACAO: Verificacao via API do GitHub.**

Este desafio e diferente dos demais: nao ha codigo para analisar. A avaliacao consiste em verificar se o commit do aluno esta assinado (badge "Verified" no GitHub).

Procedimento:
1. O aluno envia um link que pode ser:
   - Link de um repositorio (ex: `https://github.com/usuario/repo`)
   - Link de um commit especifico (ex: `https://github.com/usuario/repo/commit/SHA`)
2. Se for link de commit, extraia o owner, repo e SHA da URL.
3. Se for link de repositorio, voce precisara verificar os commits da branch main.
4. Use o comando `gh api` para verificar se o commit esta assinado:
   - `gh api repos/{owner}/{repo}/commits/{sha}` — verifique se o campo `commit.verification.verified` e `true`.
   - Se o link for de repositorio (sem SHA), use `gh api repos/{owner}/{repo}/commits?sha=main&per_page=5` para listar os commits recentes e verifique se pelo menos um esta verificado.
5. Verifique tambem se o repositorio contem um `README.md`.

## Procedimento de Avaliacao

### 1. Extrair Informacoes do Link
- Identifique se o link aponta para um commit especifico ou para o repositorio.
- Extraia owner e repo (e SHA se disponivel) da URL.

### 2. Verificar Assinatura do Commit
Use a API do GitHub via `gh api`:
- Para commit especifico: `gh api repos/{owner}/{repo}/commits/{sha} --jq '.commit.verification.verified'`
- Para repositorio: `gh api repos/{owner}/{repo}/commits?sha=main&per_page=5 --jq '.[].commit.verification.verified'`
- O resultado deve conter `true` para pelo menos um commit.

### 3. Verificar README.md
- Use `gh api repos/{owner}/{repo}/contents/README.md` para verificar se o arquivo existe.

### 4. Verificar Branch Main
- O commit assinado deve estar na branch `main`.

### 5. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O repositorio e publico e acessivel.
- Pelo menos um commit na branch main esta assinado (badge "Verified" / campo `verified: true`).
- O repositorio contem um `README.md`.
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O commit nao esta assinado (badge Verified nao encontrada)' ou 'O repositorio nao contem um README.md']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Configurar GPG no Git e GitHub para assinar commits digitalmente, garantindo que o commit exiba a badge "Verified" no historico do GitHub.

Tecnologias: Git, GPG, GitHub.

Requisitos:
1. Repositorio publico no GitHub.
2. Chave GPG configurada e vinculada ao GitHub.
3. Commit assinado com push para o repositorio.
4. Badge "Verified" visivel no historico de commits.
5. README.md presente no repositorio.

Entregavel: Link do repositorio ou do commit assinado. Branch `main`.
