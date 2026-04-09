# Guia de Devolutivas - Stress Test Go

## Como Escrever uma Devolutiva de Qualidade

### Regras de Tom e Estilo
- Tom cordial, profissional e incentivador. Nunca hostil ou condescendente.
- Portugues brasileiro. Usar o primeiro nome do aluno.
- Mencionar especificamente o que o aluno fez bem (aprovado) ou o que faltou (reprovado).
- Ir direto ao ponto, sem paragrafos genericos. Nao usar emojis.

### Estrutura Padrao
1. **Abertura**: "Ola, {Nome}!"
2. **Corpo**: Resultado + detalhes especificos
3. **Fechamento**: Incentivo + despedida

### O que NAO Fazer
- Nao copiar a mesma devolutiva para todos. Nao ser vago. Nao listar todos os requisitos cumpridos. Nao ser rude.

---

## Exemplos de Devolutivas — APROVADO

### Exemplo 1
Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos do desafio com sucesso: a CLI aceita os parametros --url, --requests e --concurrency, as requisicoes sao distribuidas com worker pool, o relatorio exibe todos os dados exigidos, e o Dockerfile permite execucao via docker run.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! O worker pool com goroutines distribui as requisicoes corretamente, o numero total e cumprido exatamente, e o relatorio e claro e completo.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. A arquitetura com channels e WaitGroup esta bem implementada, o Dockerfile usa multi-stage build com ENTRYPOINT, e o README documenta build e execucao.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O relatorio gerado ao final da execucao nao exibe a distribuicao de outros codigos de status HTTP (ex: 404, 500).

Conforme o enunciado, alem do total de requests e status 200, o relatorio deve mostrar a distribuicao de todos os outros status codes.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O Dockerfile nao permite passar parametros via linha de comando. Ao executar docker run <imagem> --url=... o container nao recebe os argumentos.

Verifique se o ENTRYPOINT aponta para o binario da aplicacao, permitindo que os parametros sejam passados como argumentos do docker run.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O numero total de requisicoes nao e cumprido exatamente. Com --requests=100 e --concurrency=10, o sistema executou 97 requisicoes.

Garanta que o numero total de requisicoes seja cumprido exatamente, independentemente do nivel de concorrencia.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
