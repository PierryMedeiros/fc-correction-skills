# Guia de Devolutivas - Docker Nginx Node.js

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

Voce cumpriu todos os requisitos com sucesso: Docker Compose com Nginx na porta 8080 como proxy reverso, aplicacao Node.js que insere nomes no MySQL e exibe 'Full Cycle Rocks!' com a lista de nomes.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! O Nginx esta configurado corretamente como proxy reverso, a aplicacao Node.js se conecta ao MySQL, e ao acessar localhost:8080 tudo funciona perfeitamente.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. O docker-compose sobe os 3 servicos (Nginx, Node.js, MySQL), a pagina exibe 'Full Cycle Rocks!' seguida dos nomes, e o README documenta a execucao.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---
## Exemplos — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Ao executar o docker compose up (sem o -d), o seguinte erro ocorreu: {erro}.

Reveja a configuracao do docker-compose.yml e garanta que todos os servicos subam corretamente.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

A pagina retornada pelo Nginx nao contem 'Full Cycle Rocks!'.

Conforme o enunciado, ao acessar localhost:8080, a pagina deve exibir '<h1>Full Cycle Rocks!</h1>' seguida de uma lista de nomes do banco.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O Node.js nao esta se conectando ao MySQL. O container da aplicacao reinicia em loop.

Verifique se ha um mecanismo de espera para o MySQL ficar pronto antes da aplicacao tentar conectar (ex: depends_on com healthcheck, dockerize, ou wait-for-it).

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
