# Guia de Devolutivas - Codeflix TS Use Cases Categoria

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
Voce cumpriu todos os requisitos: os 5 Use Cases estao implementados, npm run tsc:check passa sem erros, e a cobertura de testes e >= 80%.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! Create, Update, Delete, Get e Search/List de Categoria funcionam corretamente, a tipagem esta limpa, e a cobertura esta acima de 80%.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. Os Use Cases usam DTOs, o script tsc:check esta no package.json, e o Jest falha se cobertura < 80%.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
A cobertura de testes esta abaixo de 80%. npm run test:cov reportou {X}%.
Configure o Jest para falhar se a cobertura for inferior a 80% e adicione mais testes.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O script tsc:check nao esta configurado no package.json.
Crie um script npm chamado tsc:check que execute o compilador TypeScript para verificacao sem gerar build (ex: tsc --noEmit).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O Use Case Delete de Categoria nao foi implementado.
Os 5 Use Cases obrigatorios sao: Create, Update, Delete, Get e Search/List.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
