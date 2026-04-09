# Guia de Devolutivas - Multithreading CEP

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

Voce cumpriu todos os requisitos do desafio com sucesso: as requisicoes paralelas com goroutines para BrasilAPI e ViaCEP, o uso de channels e select para capturar a resposta mais rapida, e o timeout de 1 segundo estao implementados corretamente.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! O padrao de corrida (race condition) esta bem implementado com channels e select, a API vencedora e identificada no output, e o timeout funciona corretamente.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. O codigo e limpo, usa context.WithTimeout para o timeout de 1 segundo, e o README documenta como executar e testar.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O sistema nao implementa o timeout de 1 segundo conforme exigido pelo enunciado.

Utilize mecanismos como time.After(1 * time.Second), context.WithTimeout ou similar integrado ao select.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O sistema nao utiliza select para capturar a primeira resposta. As goroutines estao corretas, mas a logica de corrida nao esta implementada.

O padrao esperado e usar select com channels para capturar a primeira resposta que chegar, descartando a mais lenta.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O output nao identifica qual API entregou a resposta.

Conforme o enunciado, o resultado deve exibir os dados do endereco E qual API respondeu (BrasilAPI ou ViaCEP).

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
