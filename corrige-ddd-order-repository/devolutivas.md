# Guia de Devolutivas - DDD OrderRepository
## Como Escrever uma Devolutiva de Qualidade
### Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome do aluno. Mencionar detalhes especificos. Direto ao ponto. Sem emojis.
### Estrutura: 1. Abertura 2. Corpo (resultado + detalhes) 3. Fechamento (incentivo)
### NAO: copiar mesma para todos, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: a classe OrderRepository implementa os 4 metodos (create, update, find, findAll), os testes cobrem todos os cenarios, e a estrutura segue o padrao do curso.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! Os metodos manipulam corretamente a entidade Order e seus OrderItems, e os testes com Sequelize validam a persistencia.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. A estrutura de pastas segue o padrao fc-ddd-patterns, os 4 metodos estao implementados, e os testes passam.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
A classe OrderRepository nao implementa o metodo findAll.
Os 4 metodos obrigatorios sao: create, update, find e findAll. Todos devem estar implementados e testados.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O metodo update nao atualiza corretamente os OrderItems. Ao alterar itens de um pedido, os antigos nao sao removidos.
O update deve substituir os itens do pedido, garantindo consistencia entre Order e OrderItems.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
A estrutura do repositorio nao segue o padrao do curso (fc-ddd-patterns). As pastas domain/ e infrastructure/ nao estao separadas corretamente.
O projeto deve seguir a organizacao de pastas ensinada no curso, com separacao entre domain/ (entidades, repositorios, servicos) e infrastructure/ (implementacoes concretas).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
