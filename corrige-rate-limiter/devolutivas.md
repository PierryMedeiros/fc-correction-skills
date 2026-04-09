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

## Exemplo de Devolutiva — APROVADO

Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos do desafio com sucesso: middleware implementado, limitacao por IP e Token com precedencia Token > IP, HTTP 429 com mensagem correta, Redis com padrao Strategy, Docker Compose com app e Redis, e testes automatizados.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplo de Devolutiva — NAO APROVADO

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Conforme orienta o enunciado do desafio, ao executar docker compose up, tudo deve estar funcionando 100%, sem necessidade de comandos adicionais.

Dito isso, e necessario que voce crie um Dockerfile para a sua aplicacao e a adicione como servico no docker-compose.yml, garantindo que ela tambem seja executada automaticamente na porta 8080 junto com o Redis.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
