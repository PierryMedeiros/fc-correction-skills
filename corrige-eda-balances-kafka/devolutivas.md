# Guia de Devolutivas - EDA Balances Kafka

## Como Escrever uma Devolutiva de Qualidade

### Regras de Tom e Estilo
- Tom cordial, profissional e incentivador. Nunca hostil ou condescendente.
- Portugues brasileiro.
- Usar o primeiro nome do aluno.
- Mencionar especificamente o que o aluno fez bem (se aprovado) ou o que faltou (se reprovado).
- Ir direto ao ponto, sem paragrafos genericos.
- Nao usar emojis.

### Estrutura Padrao
1. **Abertura**: "Ola, {Nome}!" ou "Ola!"
2. **Corpo**: Resultado + detalhes especificos do que foi avaliado
3. **Fechamento**: Incentivo + despedida

### O que NAO Fazer
- Nao copiar e colar a mesma devolutiva para todos os alunos.
- Nao ser vago ("seu projeto tem problemas") — sempre especificar QUAIS.
- Nao listar todos os requisitos cumpridos (fica extenso) — mencionar 2-3 pontos fortes.
- Nao ser rude em reprovacoes.

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
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
