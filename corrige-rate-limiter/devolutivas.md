# Guia de Devolutivas - Rate Limiter

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

## Exemplos de Devolutivas — APROVADO

### Exemplo 1

Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos do desafio com sucesso: middleware implementado, limitacao por IP e Token com precedencia Token > IP, HTTP 429 com mensagem correta, Redis com padrao Strategy, Docker Compose com app e Redis, e testes automatizados incluindo precedencia.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2

Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos com sucesso. O padrao Strategy esta bem implementado com a interface abstraindo o Redis, a precedencia Token > IP funciona corretamente, e o Docker Compose sobe tudo automaticamente na porta 8080.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3

Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! Todos os requisitos foram atendidos. Destaco a qualidade dos testes automatizados que cobrem tanto a eficacia do limiter quanto a logica de precedencia Token sobre IP.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Conforme orienta o enunciado do desafio, ao executar docker compose up, tudo deve estar funcionando 100%, sem necessidade de comandos adicionais.

Dito isso, e necessario que voce crie um Dockerfile para a sua aplicacao e a adicione como servico no docker-compose.yml, garantindo que ela tambem seja executada automaticamente na porta 8080 junto com o Redis.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O middleware retorna HTTP 403 (Forbidden) com a mensagem 'Acesso bloqueado' ao exceder o limite.

Conforme o enunciado, o retorno deve ser HTTP 429 (Too Many Requests) com a mensagem exata: 'you have reached the maximum number of requests or actions allowed within a certain time frame'.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Nao existem testes automatizados que validem a precedencia do Token sobre o IP.

Conforme o enunciado, e obrigatorio ter testes que demonstrem que o limite do Token se sobrepoe ao limite do IP.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
