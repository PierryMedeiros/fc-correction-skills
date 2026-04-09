---
name: corrige-codeflix-upload-video
description: >
  Corrige e avalia o desafio de Catalogo de Videos - Primeiro Upload de Arquivos com Laravel.
  TRIGGER quando: desafio de catalogo de videos, codeflix, upload de video, video_file,
  upload de arquivos, primeiro upload, Laravel video, video/mp4, validacao upload,
  catalogo de video upload, code-flix, codeflix video catalog.
  Palavras-chave: catalogo de videos, codeflix, upload, video_file, video/mp4,
  Laravel, PHP, validacao, tamanho maximo, upload de arquivo, primeiro upload,
  teste upload, video catalog, storage, POST video.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Catalogo de Videos: Primeiro Upload de Arquivos

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Catalogo de Videos: Primeiro Upload de Arquivos".

**MODO DE AVALIACAO: Analise estatica + execucao de testes (se possivel).**

Alem de ler os arquivos, tente executar os testes do projeto:
1. Se houver `docker-compose.yml`, execute `docker compose up -d --build` e depois rode os testes dentro do container.
2. Se for um projeto Laravel puro, execute `composer install` e `php artisan test` (ou `./vendor/bin/phpunit`).
3. Se a execucao de testes nao for possivel (dependencias complexas, banco especifico, etc), a analise estatica e suficiente.
4. Inclua o resultado dos testes na avaliacao se conseguir executa-los.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se o projeto e uma aplicacao Laravel com:
- Estrutura de pastas padrao Laravel (ex: `app/`, `database/`, `routes/`, `tests/`, etc).
- Model de Video (ex: `app/Models/Video.php` ou similar).
- Migration para a tabela de videos.
- Controller de Video (ex: `app/Http/Controllers/VideoController.php` ou similar).
- Arquivo(s) de teste.

### 2. Analise do Campo video_file na Migration
Verifique se existe uma migration que adiciona o campo `video_file` a tabela de videos:
- O campo deve ser do tipo **string** e **nullable**.
- Pode ser uma migration nova ou uma alteracao na migration existente.

### 3. Analise da Validacao do Upload
Verifique se as regras de validacao do upload de video estao implementadas:
- O campo `video_file` **NAO deve ser required** (upload nao e obrigatorio no POST/PUT).
- Deve validar que o tipo do arquivo e **video/mp4** (ex: `mimetypes:video/mp4`, `mimes:mp4`, ou similar).
- Deve validar um **tamanho maximo** para o arquivo (ex: `max:xxxxx` — valor simbolico definido pelo aluno).

### 4. Analise dos Testes de Validacao
Verifique se existem testes que validam:
- **Invalidacao do tipo de video**: Teste que envia um arquivo com tipo diferente de video/mp4 e verifica que a validacao falha.
- **Invalidacao do tamanho maximo**: Teste que envia um arquivo maior que o limite e verifica que a validacao falha.

### 5. Analise da Implementacao do Upload
Verifique se o upload do video esta implementado:
- O upload deve funcionar via **POST** (criacao de video).
- O arquivo deve ser armazenado usando o sistema de storage do Laravel (ex: `Storage::put`, `store()`, `storeAs()`, ou similar).
- O caminho/nome do arquivo salvo deve ser persistido no campo `video_file` do banco.

### 6. Analise do Teste de Upload
Verifique se existe um teste que:
- Envia um POST com um arquivo de video (usando `UploadedFile::fake()` ou similar).
- Verifica se o arquivo foi **criado corretamente** no storage apos o cadastro (ex: `Storage::assertExists()`, `Storage::disk()->assertExists()`, ou similar).

### 7. Analise do README.md
Verifique se contem instrucoes de como rodar o projeto e os testes.

### 8. Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 9. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- O campo `video_file` existe na migration como string e nullable.
- A validacao exige tipo video/mp4 e tamanho maximo (sem ser required).
- Existem testes de invalidacao de tipo e tamanho maximo do upload.
- O upload via POST esta implementado com armazenamento no storage do Laravel.
- Existe teste que verifica se o arquivo foi criado no storage apos o cadastro.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'Nao existe teste de invalidacao do tipo de video' ou 'O campo video_file nao esta definido como nullable na migration']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Adicionar campo de upload de video ao catalogo, com validacao de tipo (video/mp4) e tamanho maximo, implementar o upload via POST, e criar testes de validacao e upload.

Tecnologias: PHP, Laravel, PHPUnit.

Requisitos:
1. Campo `video_file` (string, nullable) na tabela de videos.
2. Validacao: nao required, tipo video/mp4, tamanho maximo (valor simbolico).
3. Testes de invalidacao: tipo de video errado e tamanho maximo excedido.
4. Upload implementado via POST com armazenamento no storage.
5. Teste que verifica se o arquivo foi criado no storage apos o cadastro.

Entregavel: Repositorio unico no GitHub com implementacao, testes e README. Branch `main`.
