# Skills de Correcao de Desafios - Full Cycle

Colecao de 38 skills para o Claude Code que automatizam a correcao de desafios dos cursos Full Cycle. Cada skill avalia um desafio especifico, executa testes quando possivel e gera devolutivas personalizadas para os alunos.

## Instalacao

Clone este repositorio dentro da pasta `skills` do Claude Code na sua maquina:

```bash
cd ~/.claude/skills
git clone <url-deste-repo> correcao
```

Apos clonar, o Claude Code vai detectar automaticamente todas as skills. Nenhuma configuracao adicional e necessaria.

## Pre-requisitos

Para que as skills funcionem corretamente, sua maquina deve ter:

- **Claude Code** (CLI da Anthropic)
- **Docker e Docker Compose** (para desafios que sobem containers)
- **Go 1.21+** (para desafios Go Expert)
- **Node.js 18+ e npm** (para desafios TypeScript/Node)
- **Python 3.10+** (para desafios Python/Django)
- **gh CLI** (GitHub CLI, para o desafio de commit assinado)

## Como usar

1. Receba a lista de desafios com nome do aluno, fase do projeto e link do repositorio
2. Clone os repos dos alunos em `/aluno/`
3. Peca para o Claude Code corrigir — ele identifica automaticamente a skill correta pelo nome do desafio
4. Apos corrigir, rode `./cleanDocker.sh` para limpar containers e imagens
5. O Claude gera um relatorio com devolutivas personalizadas para cada aluno

## Estrutura de cada skill

Cada pasta de skill contem:

```
corrige-nome-do-desafio/
  SKILL.md          # A skill em si (instrucoes para a IA avaliar o desafio)
  devolutivas.md    # Guia de como escrever devolutivas + exemplos especificos
  .env.exemplo      # Template de chaves de API (copie para .env e preencha)
  README.md         # Avisos para o suporte (apenas nas skills com restricoes)
```

- `SKILL.md` — contem os criterios de avaliacao, como executar, e logica de aprovacao/reprovacao
- `devolutivas.md` — guia de tom/estilo e exemplos de devolutivas (aprovado e reprovado) especificos para aquele desafio. A IA le este arquivo antes de redigir a devolutiva ao aluno.

## Configuracao de Chaves de API

Algumas skills precisam de chaves de API para executar os desafios. Cada uma dessas skills
tem um arquivo `.env.exemplo` com os campos vazios. Para configurar:

1. Entre na pasta da skill que precisa de chave
2. Copie o `.env.exemplo` para `.env`
3. Preencha os valores no `.env`

```bash
cd corrige-temperatura-cep
cp .env.exemplo .env
# Edite o .env e preencha as chaves
```

**Skills que precisam de chave:**

| Skill | Arquivo | Chaves |
|---|---|---|
| corrige-temperatura-cep | `.env.exemplo` | `WEATHER_API_KEY`, `OPEN_WEATHERMAP_API_KEY` |
| corrige-tracing-distribuido | `.env.exemplo` | `WEATHER_API_KEY`, `OPEN_WEATHERMAP_API_KEY` |
| corrige-langchain-postgres | `.env.exemplo` | `OPENAI_API_KEY` ou `GOOGLE_API_KEY` |
| corrige-prompt-langchain | `.env.exemplo` | `OPENAI_API_KEY` ou `GOOGLE_API_KEY`, `LANGCHAIN_API_KEY` |

## Skills com correcao ESTATICA (falta de chave de API)

Os desafios abaixo sao corrigidos apenas por leitura de codigo. As chaves de API
necessarias (OpenAI, Google Gemini, LangSmith) **geram custo por uso**, e cada correcao
consome tokens da API. Por isso, a analise esta configurada como estatica por padrao.

| Skill | Chaves necessarias | Custo |
|---|---|---|
| corrige-langchain-postgres | OpenAI ou Google Gemini | Custo por tokens (ingestao + chat) |
| corrige-prompt-langchain | OpenAI/Gemini + LangSmith | Custo por tokens (avaliacao de prompts) |

Se voce tiver as chaves e aceitar o custo, pode habilitar a execucao pratica
seguindo as instrucoes abaixo.

### Como habilitar execucao pratica nesses desafios

Alem de preencher o `.env`, voce deve alterar o trecho do
`SKILL.md` de cada skill para trocar de analise estatica para execucao pratica.

**Para `corrige-langchain-postgres/SKILL.md`**, substitua este trecho:

```
**MODO DE AVALIACAO: Analise estatica + execucao de testes (se houver).**

Este desafio depende de chaves de LLM (OpenAI/Google Gemini) para executar a aplicacao. Como essas chaves podem nao estar disponiveis, a avaliacao e baseada na **leitura dos arquivos** (chunk_size, chunk_overlap, k=10, regras do prompt, PGVector).

Se o projeto contiver testes automatizados que nao dependam de chave de LLM, execute-os:
1. Execute `pip install -r requirements.txt` e `pytest` (ou equivalente) no diretorio do projeto.
2. Inclua o resultado dos testes na avaliacao.

A analise estatica dos arquivos e suficiente para aprovar ou reprovar.
```

Por este:

```
**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

**Chaves de API:** Carregue as chaves do arquivo `.env` nesta mesma pasta da skill.

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Carregue as variaveis: `export $(grep -v '^#' /caminho/para/.env | xargs)`
2. Execute `docker compose up -d` para subir o PostgreSQL.
3. Execute `pip install -r requirements.txt` e `python src/ingest.py` para testar a ingestao.
4. Execute `python src/chat.py` e faca uma pergunta de teste.
5. Ao final, execute `docker compose down -v` para limpar.
6. Inclua os resultados na avaliacao.
```

**Para `corrige-prompt-langchain/SKILL.md`**, substitua este trecho:

```
**MODO DE AVALIACAO: Analise estatica + execucao de testes (se houver).**

Este desafio depende de chaves de LLM (OpenAI/Google Gemini) e LangSmith para executar a aplicacao. Como essas chaves podem nao estar disponiveis, a avaliacao e baseada na **leitura dos arquivos** (prompt v2, 6 testes, README com resultados).

Se o projeto contiver testes automatizados que nao dependam de chave de LLM, execute-os:
1. Execute `pip install -r requirements.txt` e `pytest tests/` no diretorio do projeto.
2. Inclua o resultado dos testes na avaliacao.

A analise estatica dos arquivos e suficiente para aprovar ou reprovar.
```

Por este:

```
**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

**Chaves de API:** Carregue as chaves do arquivo `.env` nesta mesma pasta da skill.

Alem de ler os arquivos, voce DEVE executar o projeto:
1. Carregue as variaveis: `export $(grep -v '^#' /caminho/para/.env | xargs)`
2. Execute `pip install -r requirements.txt`.
3. Execute `pytest tests/` para rodar os testes.
4. Se possivel, execute os scripts de push/pull de prompts.
5. Inclua os resultados na avaliacao.
```

## Total de skills: 38

### Go Expert
- corrige-client-server-api
- corrige-multithreading-cep
- corrige-clean-architecture-go
- corrige-temperatura-cep
- corrige-stress-test-go
- corrige-rate-limiter
- corrige-tracing-distribuido
- corrige-leilao-goroutines

### Docker
- corrige-docker-nginx
- corrige-docker-go-otimizado

### Clean Architecture (TypeScript)
- corrige-clean-arch-notification-pattern
- corrige-clean-arch-validacao-product
- corrige-clean-arch-usecases-product
- corrige-clean-arch-api-product

### DDD Patterns (TypeScript)
- corrige-ddd-order-repository
- corrige-ddd-customer-events

### Sistemas Monoliticos (TypeScript)
- corrige-monolito-endpoints-api
- corrige-monolito-modulo-invoice

### Codeflix TypeScript
- corrige-codeflix-ts-entidade-categoria
- corrige-codeflix-ts-usecases-categoria
- corrige-codeflix-ts-repositorio-validacao-categoria
- corrige-codeflix-ts-endpoints-categoria-castmember
- corrige-codeflix-ts-conclusao-projeto

### Codeflix Python
- corrige-codeflix-py-api-castmember
- corrige-codeflix-py-patch-api-categoria
- corrige-codeflix-py-usecase-update-genre
- corrige-codeflix-py-update-api-genre
- corrige-codeflix-py-paginacao-refatoracao
- corrige-codeflix-py-video-api
- corrige-codeflix-py-token-jwt
- corrige-codeflix-py-teste-e2e-video

### Codeflix Laravel
- corrige-codeflix-upload-video

### Python/Django
- corrige-castmember-python

### TDD
- corrige-tdd-reservas

### IA/ML
- corrige-langchain-postgres
- corrige-prompt-langchain

### EDA
- corrige-eda-balances-kafka

### Git
- corrige-git-commit-assinado
