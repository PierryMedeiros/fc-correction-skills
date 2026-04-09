# Guia de Devolutivas - Codeflix Py Teste E2E Video
## Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome. Detalhes especificos. Direto ao ponto. Sem emojis.
## Estrutura: 1. Abertura 2. Corpo 3. Fechamento | NAO: copiar, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: o teste E2E cobre o fluxo completo (setup, criacao de video, upload, evento videos.converted, validacao status COMPLETED).
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! O teste cria as entidades, publica o evento na fila do RabbitMQ, e verifica o status final do video automaticamente.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. O fluxo end-to-end funciona, o consumer processa o evento, e o requirements.txt esta presente.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O teste E2E nao cobre o passo de publicacao do evento na fila videos.converted.
Conforme o enunciado, o teste deve publicar um evento simulando o retorno do transcoder e verificar que o status mudou para COMPLETED.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O teste nao valida se o status do video foi atualizado para MediaStatus.COMPLETED apos o evento.
A verificacao final e essencial: apos publicar o evento, confirme que o status e COMPLETED via API ou consulta ao banco.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O projeto nao contem o arquivo requirements.txt.
Conforme o enunciado, o requirements.txt e obrigatorio listando todas as dependencias do projeto Python.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
