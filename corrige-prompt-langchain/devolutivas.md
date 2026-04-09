# Guia de Devolutivas - Prompts LangChain/Smith

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
Voce cumpriu todos os requisitos: prompt v2 com tecnicas avancadas aplicadas, os 6 testes obrigatorios implementados, sem TODOs, e README completo com resultados e instrucoes.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! O prompt v2 demonstra Role Playing e Few-Shot claros, os 6 testes passam, e o README contem link do LangSmith e tabela comparativa v1 vs v2.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. O bug_to_user_story_v2.yml tem persona definida e exemplos de entrada/saida, os testes cobrem todos os cenarios, e nao ha TODOs.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
Faltam testes obrigatorios no arquivo tests/test_prompts.py.
Os 6 testes exigidos sao: test_prompt_has_system_prompt, test_prompt_has_role_definition, test_prompt_mentions_format, test_prompt_has_few_shot_examples, test_prompt_no_todos, test_minimum_techniques.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O prompt v2 ainda contem marcadores [TODO] que devem ser substituidos.
Remova todos os [TODO] e substitua pelo conteudo real. O prompt deve estar completo e funcional.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O README nao contem a secao de Resultados Finais com link publico do LangSmith.
Conforme o enunciado, o README deve ter: Tecnicas Aplicadas (Fase 2), Resultados Finais (link LangSmith + tabela v1 vs v2), e Como Executar.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
