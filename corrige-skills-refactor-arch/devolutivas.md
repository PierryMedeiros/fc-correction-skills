# Guia de Devolutivas - Criacao de Skills (Refactor-Arch)

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

Voce cumpriu todos os requisitos do desafio com sucesso: a skill refactor-arch esta presente nos 3 projetos com as 3 fases bem definidas, o catalogo contem mais de 8 anti-patterns com severidade distribuida e deteccao de APIs deprecated, e os 3 relatorios de auditoria estao no formato padronizado com arquivo e linha em cada finding.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2

Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! Destaco a qualidade do playbook de refatoracao, com exemplos antes/depois bem estruturados que tornam a skill verdadeiramente agnostica de tecnologia. Os 3 projetos ficaram organizados em MVC e os findings CRITICAL foram corrigidos corretamente.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3

Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos. A analise manual no README esta detalhada para os 3 projetos, os relatorios em reports/ seguem o template definido na skill, e a refatoracao eliminou as credenciais hardcoded e quebrou as God Classes em modulos MVC bem separados.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

A skill refactor-arch so esta presente dentro de code-smells-project. Os outros dois projetos (ecommerce-api-legacy e task-manager-api) nao contem a pasta .claude/skills/refactor-arch/.

Conforme o enunciado, a skill deve ser copiada para dentro dos 3 projetos para provar que e agnostica de tecnologia e reutilizavel.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O catalogo de anti-patterns contem apenas 5 itens, todos de severidade HIGH, e nao inclui deteccao de APIs deprecated.

Conforme o enunciado, o catalogo deve ter no minimo 8 anti-patterns, com severidade distribuida (CRITICAL, HIGH, MEDIUM, LOW) e obrigatoriamente incluir deteccao de APIs obsoletas recomendando o equivalente moderno.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O projeto ecommerce-api-legacy nao foi refatorado para o padrao MVC — o arquivo src/GodManager.js continua concentrando toda a logica de negocio, rotas e acesso a dados, mesmo tendo sido identificado como God Object no relatorio.

Conforme o enunciado, a Fase 3 da skill deve efetivamente reestruturar cada projeto em models, views/routes e controllers, corrigindo os findings CRITICAL e HIGH levantados na auditoria.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 4 (Link invalido)

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
