# Guia de Devolutivas - Clean Arch Notification Pattern

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

## Exemplo de Devolutiva — APROVADO

Ola, {Nome}!

Parabens pelo bom trabalho!

Voce cumpriu todos os requisitos do desafio com sucesso: a entidade Product utiliza o Notification Pattern para acumular erros, as validacoes estao mantidas, e o teste de multiplos erros simultaneos esta implementado.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplo de Devolutiva — NAO APROVADO

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Conforme o enunciado, e obrigatorio criar um teste especifico que force dois erros de validacao simultaneos.

Esse teste nao foi encontrado no repositorio. Crie um teste que force Name vazio e Price negativo ao mesmo tempo e verifique se a notificacao contem ambos os erros.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
