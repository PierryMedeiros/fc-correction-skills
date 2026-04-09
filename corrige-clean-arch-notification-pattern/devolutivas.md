# Guia de Devolutivas - Clean Arch Notification Pattern

## Como Escrever uma Devolutiva de Qualidade
### Regras de Tom e Estilo
- Tom cordial, profissional e incentivador. Portugues brasileiro. Usar o primeiro nome do aluno.
- Mencionar especificamente o que fez bem (aprovado) ou o que faltou (reprovado). Ir direto ao ponto. Nao usar emojis.
### Estrutura: 1. Abertura ("Ola, {Nome}!") 2. Corpo (resultado + detalhes) 3. Fechamento (incentivo + despedida)
### NAO Fazer: copiar mesma devolutiva para todos, ser vago, listar todos os requisitos, ser rude.

---
## Exemplos — APROVADO

### Exemplo 1
Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos com sucesso: a entidade Product utiliza o Notification Pattern para acumular erros, as validacoes estao mantidas, e o teste de multiplos erros simultaneos esta implementado.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! O ProductYupValidator acumula erros na notificacao sem lancar excecoes, e o teste de dois erros simultaneos verifica ambos na notificacao.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. A entidade Product nao lanca excecoes diretamente, usa entity.notification.addError(), e o teste obrigatorio de multiplos erros esta presente e passa.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---
## Exemplos — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Nao existe um teste especifico que force dois erros de validacao simultaneos (ex: Name vazio e Price negativo ao mesmo tempo).

Esse teste e obrigatorio conforme o enunciado. Crie um teste que force Name vazio e Price negativo e verifique se a notificacao contem ambos os erros.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

A entidade Product ainda lanca excecoes (throw new Error) ao inves de usar o Notification Pattern.

A entidade deve adicionar erros a notificacao (this.notification.addError) em vez de lancar excecoes imediatas.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O repositorio nao contem um arquivo README.md com instrucoes de como rodar os testes.

Conforme o enunciado, o README deve conter instrucoes de execucao dos testes.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
