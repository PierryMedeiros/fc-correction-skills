# Guia de Devolutivas - DDD Eventos de Customer
## Como Escrever uma Devolutiva de Qualidade
### Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome do aluno. Mencionar detalhes especificos. Direto ao ponto. Sem emojis.
### Estrutura: 1. Abertura 2. Corpo (resultado + detalhes) 3. Fechamento (incentivo)
### NAO: copiar mesma para todos, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: os eventos CustomerCreatedEvent e CustomerAddressChangedEvent estao implementados, os handlers imprimem as mensagens corretas, e todos os testes passam.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! Os dois handlers do CustomerCreated e o handler do CustomerAddressChanged imprimem as mensagens exatas do enunciado, e os testes validam o disparo com spyOn.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. O EventDispatcher registra os handlers corretamente, os eventos sao disparados nos momentos certos, e a estrutura segue o padrao fc-ddd-patterns.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O evento CustomerAddressChangedEvent nao esta implementado.
Conforme o enunciado, devem existir dois eventos: CustomerCreated (com 2 handlers) e CustomerAddressChanged (com 1 handler que imprime id, nome e endereco).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O handler EnviaConsoleLog1Handler nao imprime a mensagem correta.
A mensagem deve ser: 'Esse e o primeiro console.log do evento: CustomerCreated' (ou equivalente com mesmo sentido).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
Nao existem testes automatizados que validem o disparo dos eventos e execucao dos handlers.
O enunciado exige testes que verifiquem que os handlers sao chamados ao disparar os eventos (use spyOn ou similar).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
