# Guia de Devolutivas - Docker Go Otimizado

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

Voce cumpriu todos os requisitos do desafio com sucesso: a aplicacao Go imprime 'Full Cycle Rocks!!', o Dockerfile utiliza multi-stage build com imagem final scratch, e a imagem resultante tem menos de 2MB.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 2

Ola, {Nome}!

Parabens pelo bom trabalho!

Excelente trabalho! A imagem Docker tem apenas {X}KB, bem abaixo do limite de 2MB. O uso de scratch como imagem base e as flags de otimizacao demonstram dominio das tecnicas de otimizacao de imagens.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

### Exemplo 3

Ola, {Nome}!

Parabens pelo bom trabalho!

Todos os requisitos atendidos. O Dockerfile esta otimizado com multi-stage build, a imagem final e minima, e o README contem o nome real da imagem no Docker Hub com o comando para execucao.

Continue com esse ritmo de dedicacao, seu progresso esta nitido!

Bons estudos e ate o proximo desafio!

Abraco!

---

## Exemplos de Devolutivas — NAO APROVADO

### Exemplo 1

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

A imagem Docker construida tem {X}MB, excedendo o limite de 2MB exigido pelo enunciado.

Pesquise sobre tecnicas de otimizacao como multi-stage build com imagem scratch e flags de compilacao como CGO_ENABLED=0 e -ldflags='-s -w'.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 2

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O README.md nao contem o nome real da imagem no Docker Hub. Encontramos apenas um placeholder generico como '<seu-usuario/imagem>'.

Por favor, publique a imagem no Docker Hub e atualize o README com o nome concreto da imagem e o comando exato para execucao (ex: docker run seu-usuario/fullcycle).

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!

### Exemplo 3

Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O output do container nao e exatamente 'Full Cycle Rocks!!'.

Verifique se o fmt.Println no main.go imprime exatamente 'Full Cycle Rocks!!' (com dois pontos de exclamacao).

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
### Exemplo 4 (Link invalido)
Ola, {Nome}!

Obrigado por enviar a sua resposta ao exercicio!

O link enviado nao aponta para um repositorio valido ou acessivel. Verifique se o repositorio e publico e se o link esta correto.

Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.

Bom trabalho!
