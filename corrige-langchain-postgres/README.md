# Aviso para o Suporte

Este desafio (Ingestao e Busca Semantica com LangChain e Postgres) e corrigido
apenas de forma ESTATICA por enquanto.

Motivo: Falta de chaves de API (OpenAI ou Google Gemini) para executar a aplicacao.

A skill analisa o codigo-fonte verificando:
- chunk_size=1000 e chunk_overlap=150
- k=10 na busca vetorial
- Regras do prompt de nao-alucinacao
- Uso de PGVector
- Estrutura de arquivos obrigatoria

Quando as chaves forem obtidas, preencha o arquivo .env nesta pasta
e atualize a skill para incluir execucao pratica.
