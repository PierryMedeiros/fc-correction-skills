# Guia de Devolutivas - Monolito Endpoints API

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
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: os 4 endpoints estao implementados (POST /products, POST /clients, POST /checkout, GET /invoice/:id), os testes E2E passam, e a estrutura modular esta correta.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! A camada de API esta bem integrada com os Use Cases, os testes com Supertest cobrem os 4 endpoints, e a estrutura modular segue o padrao fc-monolito.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. Os endpoints funcionam, os testes validam status code e corpo da resposta, e o README documenta a execucao.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
Nao existe teste E2E para o endpoint POST /clients.
Conforme o enunciado, todos os 4 endpoints devem possuir testes E2E com Supertest.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O endpoint POST /checkout nao esta implementado.
Os 4 endpoints obrigatorios sao: POST /products, POST /clients, POST /checkout e GET /invoice/:id.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
A estrutura do projeto nao segue o padrao modular do curso (fc-monolito). As pastas de modulos nao estao organizadas em src/modules/.
O projeto deve seguir a organizacao modular com pastas separadas para cada modulo (product-adm, client-adm, checkout, invoice, payment, store-catalog).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
