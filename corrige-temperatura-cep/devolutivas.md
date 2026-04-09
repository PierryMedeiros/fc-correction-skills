# Guia de Devolutivas - Temperatura por CEP

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

Voce cumpriu todos os requisitos do desafio com sucesso: validacao de CEP, consultas ao ViaCEP e WeatherAPI, conversoes de temperatura corretas, testes automatizados presentes, e README com URL do Google Cloud Run.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! Os tres cenarios do contrato estao corretos (200 com temperaturas, 422 invalid zipcode, 404 can not find zipcode), os testes cobrem conversoes e validacao, e a aplicacao esta publicada no Cloud Run.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. O Dockerfile esta otimizado, as formulas de conversao (F=C*1.8+32, K=C+273) estao corretas, e o README tem a URL do Cloud Run com instrucoes claras.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O README.md nao contem a URL do sistema no Google Cloud Run.

Por favor, coloque o link do Google Cloud Run onde voce subiu a aplicacao, no README.md.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

Nao existem testes automatizados que validem as conversoes de temperatura.

Conforme o enunciado, o projeto deve conter testes que comprovem o funcionamento das conversoes (Celsius para Fahrenheit e Kelvin) e da validacao de CEP.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O sistema retorna HTTP 200 para CEPs invalidos em vez de HTTP 422 com 'invalid zipcode'.

O sistema deve validar que o CEP tem exatamente 8 digitos. Se nao tiver, deve retornar 422 com a mensagem 'invalid zipcode'.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
