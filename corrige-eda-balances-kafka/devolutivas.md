# Guia de Devolutivas - EDA Balances Kafka
## Como Escrever uma Devolutiva de Qualidade
### Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome do aluno. Mencionar detalhes especificos. Direto ao ponto. Sem emojis.
### Estrutura: 1. Abertura 2. Corpo (resultado + detalhes) 3. Fechamento (incentivo)
### NAO: copiar mesma para todos, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: o microsservico Balances consome eventos do Kafka, persiste saldos no banco, o endpoint GET /balances/{account_id} funciona na porta 3003, e o Docker Compose sobe todo o ecossistema.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! A arquitetura orientada a eventos esta correta, o consumer processa transacoes do Wallet Core, e as migrations/seeds rodam automaticamente.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. O docker-compose orquestra Kafka, Wallet Core, Balances e bancos, o endpoint retorna o saldo, e o api.http facilita os testes.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O Docker Compose nao sobe o ecossistema completo. Falta o servico do Kafka.
Conforme o enunciado, o docker-compose deve orquestrar: Kafka (e Zookeeper), Wallet Core, Balances e bancos de dados.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O endpoint GET /balances/{account_id} nao esta implementado ou nao roda na porta 3003.
Conforme o enunciado, o microsservico deve expor GET /balances/{account_id} na porta 3003, retornando o saldo da conta.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
As migrations e seeds nao sao executadas automaticamente ao subir o docker-compose.
Conforme o enunciado, ao rodar docker compose up -d, as tabelas devem ser criadas e dados ficticios inseridos sem scripts manuais.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
