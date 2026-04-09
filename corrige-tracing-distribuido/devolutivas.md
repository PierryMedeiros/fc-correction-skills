# Guia de Devolutivas - Tracing Distribuido

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

Voce cumpriu todos os requisitos do desafio com sucesso: os dois microsservicos estao instrumentados com OpenTelemetry, com spans manuais para busca de CEP e temperatura, propagacao de contexto entre os servicos, e o Docker Compose sobe os 4 servicos necessarios.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2

Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! A arquitetura esta correta com Servico A validando e encaminhando, Servico B orquestrando ViaCEP e WeatherAPI, e o tracing distribuido visivel no Zipkin com spans bem nomeados.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3

Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. A propagacao de contexto via otelhttp funciona corretamente, os spans manuais permitem visualizar o fluxo completo no Zipkin, e o README documenta como fazer o POST e acessar o Zipkin.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O Servico B nao cria spans manuais para a busca de CEP e temperatura.

Conforme o enunciado, o codigo deve criar spans especificos para a busca de CEP (chamada ao ViaCEP) e busca de temperatura (chamada ao WeatherAPI), usando tracer.Start().

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O docker-compose nao inclui o OTEL Collector.

O enunciado exige 4 servicos: Servico A, Servico B, OTEL Collector e Zipkin. Adicione o OTEL Collector como intermediario entre os servicos e o Zipkin.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Nao ha propagacao de contexto de tracing entre o Servico A e o Servico B.

Utilize otelhttp.NewTransport para o cliente HTTP do Servico A e otel.GetTextMapPropagator().Extract/Inject para propagar o contexto de tracing entre os servicos.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
