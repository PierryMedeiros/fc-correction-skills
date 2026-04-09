# Guia de Devolutivas - Codeflix Py PATCH API Categoria
## Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome. Detalhes especificos. Direto ao ponto. Sem emojis.
## Estrutura: 1. Abertura 2. Corpo 3. Fechamento | NAO: copiar, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: metodo partial_update implementado, serializer com partial=True, e testes validam atualizacao parcial isolada de cada campo.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! O PATCH atualiza apenas os campos enviados, os demais permanecem inalterados, e os testes verificam isso explicitamente.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. Os 3 testes (apenas name, apenas description, apenas is_active) passam e verificam que campos nao enviados ficaram inalterados.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
Faltam testes de atualizacao parcial isolada. Nao ha teste que envie apenas is_active.
Conforme o enunciado, deve haver testes separados para: apenas name, apenas description, e apenas is_active.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O metodo partial_update nao esta implementado na view.
Adicione o metodo partial_update com a assinatura def partial_update(self, request, pk: UUID = None) -> Response.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O PATCH esta atualizando todos os campos em vez de apenas os enviados. Campos nao enviados estao sendo zerados.
Use partial=True no serializer ou crie um serializer com required=False para que apenas os campos do payload sejam atualizados.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
