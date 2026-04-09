# Guia de Devolutivas - Clean Arch API Product

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

Voce cumpriu todos os requisitos com sucesso: o endpoint GET /product esta implementado, chama o Use Case ListProduct, retorna JSON com status 200, e o teste E2E valida o fluxo completo.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! A rota esta registrada no Express, o serializer formata a saida corretamente, e o teste com Supertest valida status code e corpo da resposta.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. O endpoint de listagem funciona, o teste E2E simula uma requisicao real, e o README documenta como rodar.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---
## Exemplos — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Nao existe teste E2E para a listagem de produtos.

Conforme o enunciado, e indispensavel a criacao de um teste com Supertest que valide status code 200 e corpo da resposta.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O endpoint GET /product nao esta implementado. Nao foi encontrada uma rota para listagem de produtos.

Crie uma rota GET /product (ou /products) que chame o Use Case ListProduct e retorne JSON.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O teste E2E nao valida o corpo da resposta, apenas o status code.

Conforme o enunciado, o teste deve validar tanto o status code (200) quanto o corpo da resposta (lista de produtos em JSON).

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
