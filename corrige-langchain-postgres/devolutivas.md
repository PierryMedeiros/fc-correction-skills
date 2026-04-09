# Guia de Devolutivas - LangChain e Postgres
## Como Escrever uma Devolutiva de Qualidade
### Regras: Tom cordial, profissional, incentivador. PT-BR. Primeiro nome do aluno. Mencionar detalhes especificos. Direto ao ponto. Sem emojis.
### Estrutura: 1. Abertura 2. Corpo (resultado + detalhes) 3. Fechamento (incentivo)
### NAO: copiar mesma para todos, ser vago, listar tudo, ser rude.
---
## APROVADO
### Exemplo 1
Ola, {Nome}!
Parabens pelo bom trabalho!
Voce cumpriu todos os requisitos: ingestao com chunk_size=1000 e chunk_overlap=150, PGVector, busca com k=10, e prompt com todas as regras de nao-alucinacao.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 2
Ola, {Nome}!
Parabens pelo bom trabalho!
Excelente trabalho! O PyPDFLoader carrega o PDF, o RecursiveCharacterTextSplitter fragmenta com os parametros corretos, e o prompt contem as 4 regras obrigatorias.
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
### Exemplo 3
Ola, {Nome}!
Parabens pelo bom trabalho!
Todos os requisitos atendidos. A estrutura de arquivos esta completa (docker-compose, requirements.txt, .env.example, src/ingest.py, search.py, chat.py, document.pdf, README).
Continue com esse ritmo de dedicacao, seu progresso esta nitido!
Bons estudos e ate o proximo desafio!
Abraco!
---
## NAO APROVADO
### Exemplo 1
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
A fragmentacao de texto em src/ingest.py nao utiliza chunk_overlap=150. O valor encontrado foi 200.
O enunciado exige explicitamente chunk_size=1000 e chunk_overlap=150.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 2
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
A busca vetorial nao esta parametrizada para buscar 10 resultados. Nao foi encontrado k=10 no codigo.
Conforme o enunciado, a busca deve utilizar k=10 na funcao similarity_search ou equivalente.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
### Exemplo 3
Ola, {Nome}!
Obrigado por enviar a sua resposta ao exercicio!
O prompt nao contem a regra 'Nunca invente ou use conhecimento externo'.
O prompt deve conter as 4 regras obrigatorias: responda somente com base no contexto, se nao estiver no contexto diga que nao tem informacoes, nunca invente, nunca produza opinioes.
Reveja esse ponto e, quando finalizar, envie o projeto novamente para correcao.
Bom trabalho!
