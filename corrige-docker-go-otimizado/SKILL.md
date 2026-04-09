---
name: corrige-docker-go-otimizado
description: >
  Corrige e avalia o desafio de Docker com Go - Imagem otimizada menor que 2MB.
  TRIGGER quando: desafio de docker go, desafio go docker, imagem docker go,
  Full Cycle Rocks, docker hub go, imagem otimizada, scratch, multi-stage build,
  menos de 2MB, docker run go, iniciando com docker go, desafio go.
  Palavras-chave: docker, go, golang, imagem otimizada, scratch, multi-stage,
  2MB, Full Cycle Rocks, docker hub, docker run, Dockerfile, iniciando com docker.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Docker com Go (Imagem Otimizada)

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Iniciando com Docker - Desafio Go".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Leia o `README.md` e verifique se contem o **nome real da imagem no Docker Hub** (ex: `usuario/fullcycle`) ou um link direto para o Docker Hub. Se o README contem apenas placeholders genericos como `<nome-da-imagem>`, `<seu-usuario/imagem>`, `seu-usuario/fullcycle` (sem substituir pelo nome real), isso NAO e valido — o aluno precisa ter colocado o nome concreto da imagem dele.
2. Execute `docker build -t desafio-go-test .` no diretorio do projeto.
3. Verifique o tamanho da imagem com `docker image ls desafio-go-test --format '{{.Size}}'` — deve ser **menor que 2MB**.
4. Execute `docker run --rm desafio-go-test` e verifique se o output e exatamente `Full Cycle Rocks!!`.
5. Ao final, remova a imagem com `docker rmi desafio-go-test`.
6. Inclua os resultados da execucao (tamanho da imagem e output) na sua avaliacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos obrigatorios existem:
- `Dockerfile` (para construcao da imagem).
- `main.go` (codigo-fonte da aplicacao em Go).
- `README.md` com instrucoes.

### 2. Analise do Codigo Go (`main.go`)
Verifique se:
- O codigo imprime exatamente `Full Cycle Rocks!!` no terminal (via `fmt.Println`, `fmt.Print`, ou similar).
- O codigo e uma aplicacao Go valida com `package main` e `func main()`.

### 3. Analise do Dockerfile
Verifique se o Dockerfile utiliza tecnicas de otimizacao para reduzir o tamanho:
- **Multi-stage build** e o padrao esperado (build em uma imagem Go, copia do binario para imagem final minima).
- A imagem final deve usar **scratch**, **alpine** (muito pequena), ou similar.
- O binario deve ser compilado com flags de otimizacao (ex: `CGO_ENABLED=0`, `-ldflags="-s -w"`, ou similar).

### 4. Analise do README.md
Verifique se o README contem:
- O **nome real e concreto da imagem no Docker Hub** (ex: `joaosilva/fullcycle`, `meuusuario/desafio-go`) — NAO pode ser um placeholder generico.
- O **comando exato para rodar** (ex: `docker run joaosilva/fullcycle`).
- Se o README nao contem o nome real da imagem (apenas placeholders), isso indica que o aluno provavelmente nao publicou a imagem no Docker Hub.

### 5. Execucao e Validacao
Conforme descrito no bloco de MODO DE AVALIACAO acima:
- Build da imagem localmente.
- Verificacao do tamanho (< 2MB).
- Verificacao do output (`Full Cycle Rocks!!`).

### 6. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Os arquivos obrigatorios estao presentes (Dockerfile, main.go, README.md).
- O codigo Go imprime `Full Cycle Rocks!!`.
- O Dockerfile utiliza tecnicas de otimizacao (multi-stage build, scratch/alpine, flags de compilacao).
- A imagem construida tem menos de 2MB.
- Ao executar `docker run`, o output e `Full Cycle Rocks!!`.
- O README contem o nome real da imagem no Docker Hub (nao um placeholder) e o comando para rodar.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'A imagem Docker tem 5.2MB, excedendo o limite de 2MB' ou 'O README.md nao contem o nome real da imagem no Docker Hub' ou 'O output do container nao e Full Cycle Rocks!!']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Criar e publicar uma imagem Docker que execute uma aplicacao em Go que imprime "Full Cycle Rocks!!" no terminal. A imagem final deve ter menos de 2MB.

Tecnologias: Go, Docker, Docker Hub.

Requisitos:
1. Aplicacao Go que imprime `Full Cycle Rocks!!`.
2. Dockerfile com otimizacao (multi-stage build, scratch, flags de compilacao).
3. Imagem final publicada no Docker Hub com menos de 2MB.
4. README com nome real da imagem no Docker Hub e comando para executar.

Entregavel: Repositorio unico no GitHub com main.go, Dockerfile e README. Branch `main`.
