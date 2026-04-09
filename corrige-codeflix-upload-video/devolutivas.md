# Guia de Devolutivas - Codeflix Upload Video (Laravel)
## Como Escrever uma Devolutiva de Qualidade
### Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome do aluno. Mencionar detalhes especificos. Direto ao ponto. Sem emojis.
### Estrutura: 1. Abertura 2. Corpo (resultado + detalhes) 3. Fechamento (incentivo)
### NAO: copiar mesma para todos, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: o campo video_file esta na migration como string e nullable, a validacao exige tipo video/mp4 e tamanho maximo, o upload via POST funciona, e os testes validam o fluxo.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! A validacao rejeita tipos diferentes de video/mp4 e arquivos acima do tamanho maximo, o upload armazena no storage do Laravel, e o teste com UploadedFile::fake() confirma a criacao.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. O campo nao e required no POST/PUT, a validacao de tipo e tamanho funciona, e os testes cobrem invalidacao e upload.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
Nao existe teste de invalidacao do tipo de video.
Conforme o enunciado, deve haver testes que validem a rejeicao de tipos diferentes de video/mp4.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O campo video_file nao esta definido como nullable na migration.
Conforme o enunciado, o campo deve ser string e nullable, ja que o upload nao e obrigatorio.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
Nao existe teste que verifique se o arquivo foi criado no storage apos o upload.
Conforme o enunciado, use Storage::assertExists() ou similar para verificar que o arquivo foi armazenado corretamente.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
