# Guia de Devolutivas - Client-Server-API

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

Voce cumpriu todos os requisitos do desafio com sucesso: o servidor opera na porta 8080 com os timeouts corretos (200ms para API, 10ms para banco), o cliente faz a requisicao com timeout de 300ms e salva corretamente no cotacao.txt.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2
Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! O uso de context.WithTimeout esta correto nos tres pontos (200ms API, 10ms DB, 300ms cliente), o SQLite persiste as cotacoes, e o formato 'Dolar: {valor}' esta no cotacao.txt.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3
Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. A separacao entre server.go e client.go esta clara, os logs de timeout sao exibidos no console, e o README documenta a execucao de ambos.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O server.go nao utiliza context.WithTimeout com 200ms para a chamada a API externa.

Conforme o enunciado, os timeouts devem ser: 200ms para API externa (awesomeapi), 10ms para persistencia no SQLite, e 300ms para o cliente.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O client.go nao salva a cotacao no arquivo cotacao.txt no formato exigido.

O formato deve ser exatamente 'Dolar: {valor}' (ex: 'Dolar: 5.43').

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O server.go nao persiste a cotacao em banco de dados SQLite.

Conforme o enunciado, cada cotacao recebida deve ser registrada no SQLite com context.WithTimeout de 10ms.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
