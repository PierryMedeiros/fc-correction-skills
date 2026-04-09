# Guia de Devolutivas - Leilao Go Routines

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

Voce cumpriu todos os requisitos do desafio com sucesso: a goroutine para fechamento automatico do leilao esta implementada, a duracao e configuravel via AUCTION_DURATION, o update no MongoDB funciona, e o teste automatizado valida o fechamento.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! A goroutine com time.NewTimer nao bloqueia a thread principal, a variavel AUCTION_DURATION e parseada corretamente, e o teste com testcontainers valida o fluxo completo.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. O fechamento automatico funciona com time.After/select, o status muda para Completed no MongoDB, e o Docker Compose sobe app + banco.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O arquivo create_auction.go nao contem a implementacao de uma goroutine para fechamento automatico do leilao.

Conforme o enunciado, ao criar um leilao, uma goroutine deve ser iniciada com go func() ou go nomeDaFuncao() para monitorar o tempo e fechar o leilao automaticamente.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

A duracao do leilao esta hardcoded (ex: time.Sleep(5 * time.Minute)) em vez de vir de variavel de ambiente.

Conforme o enunciado, a duracao deve ser configuravel via variavel de ambiente AUCTION_DURATION, usando os.Getenv e time.ParseDuration.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Nao existe teste automatizado que valide o fechamento automatico do leilao.

O enunciado exige um teste que crie um leilao, aguarde o tempo configurado, e verifique se o status mudou para fechado/completed.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
