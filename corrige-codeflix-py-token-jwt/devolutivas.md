# Guia de Devolutivas - Codeflix Py Token JWT
## Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome. Detalhes especificos. Direto ao ponto. Sem emojis.
## Estrutura: 1. Abertura 2. Corpo 3. Fechamento | NAO: copiar, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: token JWT gerado com RS256 e par de chaves RSA, payload replica estrutura Keycloak com realm_access.roles, e testes usam o token para autenticar.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! O PyJWT assina com RS256, as chaves sao acessadas via variaveis de ambiente, e os testes de integracao validam permissoes reais sem mockar.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. O payload contem admin nos roles, a assinatura e RS256, e o requirements.txt inclui PyJWT e cryptography.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O token JWT nao utiliza o algoritmo RS256. Foi encontrado HS256 no codigo.
Conforme o enunciado, deve usar RS256 com par de chaves RSA (privada para assinar, publica para verificar).
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O payload do token nao contem a estrutura realm_access.roles do Keycloak.
O payload deve ser: {realm_access: {roles: ['offline_access', 'admin', 'uma_authorization', 'default-roles-codeflix']}}.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
As chaves RSA estao hardcoded no codigo de producao em vez de variaveis de ambiente.
Conforme o enunciado, as chaves devem ser acessadas atraves de variaveis de ambiente.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
