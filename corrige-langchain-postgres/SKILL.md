---
name: corrige-langchain-postgres
description: >
  Corrige e avalia o desafio de Ingestao e Busca Semantica com LangChain e Postgres.
  TRIGGER quando: desafio de langchain, postgres, pgvector, RAG, ingestao de PDF, busca semantica,
  embeddings, similarity search, vector store, vector database, recuperacao de informacao,
  chunk, chunk_size, chunk_overlap, PyPDFLoader, PGVector, similarity_search_with_score.
  Palavras-chave: langchain, postgres, pgvector, ingestao, busca semantica, RAG, PDF, embeddings,
  vector store, search, chat, prompt, python, docker compose.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Ingestao e Busca Semantica com LangChain e Postgres

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Ingestao e Busca Semantica com LangChain e Postgres".

**MODO DE AVALIACAO: Analise estatica + execucao de testes (se houver).**

Este desafio depende de chaves de LLM (OpenAI/Google Gemini) para executar a aplicacao. Essas chaves **geram custo por uso** (cada correcao consome tokens da API), por isso a avaliacao esta configurada como estatica por padrao, baseada na **leitura dos arquivos** (chunk_size, chunk_overlap, k=10, regras do prompt, PGVector).

Se o projeto contiver testes automatizados que nao dependam de chave de LLM, execute-os:
1. Execute `pip install -r requirements.txt` e `pytest` (ou equivalente) no diretorio do projeto.
2. Inclua o resultado dos testes na avaliacao.

A analise estatica dos arquivos e suficiente para aprovar ou reprovar.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos obrigatorios existem:
- `docker-compose.yml`
- `requirements.txt`
- `.env` ou `.env.example`
- `src/ingest.py`
- `src/search.py`
- `src/chat.py`
- `document.pdf` (pode ter outro nome, desde que seja um PDF na raiz do projeto)
- `README.md`

### 2. Analise de Ingestao (`src/ingest.py`)
- Verifique se o documento PDF e carregado adequadamente (ex: usando `PyPDFLoader`).
- Verifique se o texto e fragmentado utilizando `RecursiveCharacterTextSplitter`.
- **Regra Critica:** O particionamento deve configurar explicitamente `chunk_size=1000` e `chunk_overlap=150`.
- Verifique se o codigo insere/salva os vetores no banco de dados PostgreSQL usando `PGVector` (ou similar compativel com o ecossistema LangChain especificado).

### 3. Analise de Busca e Conversa (`src/search.py` e `src/chat.py`)
- **Regra Critica:** A busca vetorial deve recuperar os 10 resultados mais relevantes (utilizando `k=10` na funcao `similarity_search_with_score` ou equivalente).
- O prompt configurado no codigo para enviar a LLM deve conter as seguintes instrucoes/regras fundamentais:
  - "Responda somente com base no CONTEXTO."
  - "Se a informacao nao estiver explicitamente no CONTEXTO, responda: 'Nao tenho informacoes necessarias para responder sua pergunta.'"
  - "Nunca invente ou use conhecimento externo."
  - "Nunca produza opinioes ou interpretacoes alem do que esta escrito."

### 4. Analise do `README.md`
- Verifique se o arquivo contem instrucoes de execucao, englobando como subir o banco de dados via Docker (`docker compose up -d`), como executar a ingestao (`python src/ingest.py`) e como rodar o chat (`python src/chat.py`).

### Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Todos os arquivos e diretorios obrigatorios estao presentes e nao-vazios.
- O `ingest.py` realiza o particionamento do texto usando exatamente `chunk_size=1000` e `chunk_overlap=150`, e utiliza `PGVector`.
- A busca (`search.py` ou `chat.py`) esta parametrizada para buscar 10 resultados (`k=10`).
- O prompt inserido no codigo obedece rigorosamente as restricoes de resposta ("fora de contexto").
- O `README.md` instrui corretamente a execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'A fragmentacao de texto em src/ingest.py nao utiliza chunk_size=1000 e chunk_overlap=150' ou 'A busca nao esta solicitando k=10 resultados']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Entregar um software capaz de ler um PDF, salvar embeddings no PostgreSQL com pgVector, e permitir busca via CLI com regras estritas de nao-alucinacao.

Tecnologias: Python, LangChain, PostgreSQL + pgVector, Docker Compose.

Requisitos de Codigo:
1. Ingestao (src/ingest.py): Dividir em chunks de 1000 com overlap de 150. Converter para embeddings. Salvar no PostgreSQL (PGVector).
2. Consulta via CLI (src/chat.py): Buscar k=10 no vector store. Prompt com regras rigorosas:
"REGRAS:
- Responda somente com base no CONTEXTO.
- Se a informacao nao estiver explicitamente no CONTEXTO, responda:
  'Nao tenho informacoes necessarias para responder sua pergunta.'
- Nunca invente ou use conhecimento externo.
- Nunca produza opinioes ou interpretacoes alem do que esta escrito."

Estrutura Obrigatoria:
- docker-compose.yml, requirements.txt, .env.example, src/ingest.py, src/search.py, src/chat.py, document.pdf, README.md.
