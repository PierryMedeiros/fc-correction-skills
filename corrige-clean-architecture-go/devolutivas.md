# Guia de Devolutivas - Clean Architecture Go

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

Voce cumpriu todos os requisitos do desafio com sucesso: o ListOrdersUseCase esta implementado, as tres interfaces (REST, gRPC e GraphQL) estao expostas, as migracoes sao aplicadas automaticamente, e o README contem as portas dos servicos.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! O desacoplamento esta correto com um unico Use Case exposto via REST, gRPC e GraphQL simultaneamente. O Docker Compose sobe banco e aplicacao, e o api.http facilita os testes.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. As migracoes rodam automaticamente com docker compose up, o Dockerfile usa multi-stage build, e as tres interfaces retornam os dados corretamente.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Conforme orienta o enunciado, ao executar docker compose up, tudo deve estar funcionando automaticamente.

As migracoes nao sao aplicadas automaticamente. E necessario adicionar a execucao das migracoes no startup da aplicacao ou no docker-compose.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O sistema nao expoe a listagem de orders via gRPC.

Conforme o enunciado, o Use Case ListOrders deve ser acessivel via REST (GET /order), gRPC (Service ListOrders) e GraphQL (Query ListOrders).

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O arquivo api.http nao contem requisicoes para criar e listar orders.

Conforme o enunciado, o api.http deve conter exemplos de POST para criar orders e GET para listar.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
