---
name: corrige-prompt-langchain
description: >
  Corrige e avalia o desafio de Pull, Otimizacao e Avaliacao de Prompts com LangChain e LangSmith.
  TRIGGER quando: desafio de prompt engineering, prompt optimization, LangChain, LangSmith,
  few-shot, chain of thought, CoT, role prompting, YAML prompt, push prompt, pull prompt,
  avaliacao de prompt, metricas de prompt, tone score, completeness, user story, bug report.
  Palavras-chave: prompt, langchain, langsmith, few-shot, CoT, role prompting, YAML,
  push, pull, avaliacao, metricas, tone, completeness, acceptance criteria, user story, python.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Pull, Otimizacao e Avaliacao de Prompts com LangChain e LangSmith

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Pull, Otimizacao e Avaliacao de Prompts com LangChain e LangSmith".

**MODO DE AVALIACAO: Analise estatica + execucao de testes (se houver).**

Este desafio depende de chaves de LLM (OpenAI/Google Gemini) e LangSmith para executar a aplicacao. Essas chaves **geram custo por uso** (cada correcao consome tokens da API), por isso a avaliacao esta configurada como estatica por padrao, baseada na **leitura dos arquivos** (prompt v2, 6 testes, README com resultados).

Se o projeto contiver testes automatizados que nao dependam de chave de LLM, execute-os:
1. Execute `pip install -r requirements.txt` e `pytest tests/` no diretorio do projeto.
2. Inclua o resultado dos testes na avaliacao.

A analise estatica dos arquivos e suficiente para aprovar ou reprovar.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos obrigatorios existem e nao estao vazios:
- `prompts/bug_to_user_story_v2.yml`
- `tests/test_prompts.py`
- `src/pull_prompts.py`
- `src/push_prompts.py`
- `README.md`
- `.env` (ou `.env.example` preenchido)

### 2. Analise do Prompt Otimizado (`prompts/bug_to_user_story_v2.yml`)
- Verifique se o arquivo contem as tecnicas solicitadas (Few-shot, CoT, Role Prompting, etc).
- Deve haver definicao de persona (ex: "Voce e um Product Manager").
- Deve haver exemplos de entrada/saida (Few-shot).
- Nao deve conter marcadores `[TODO]`.

### 3. Analise dos Testes (`tests/test_prompts.py`)
Verifique se os 6 testes obrigatorios estao implementados usando `pytest`:
- `test_prompt_has_system_prompt`
- `test_prompt_has_role_definition`
- `test_prompt_mentions_format`
- `test_prompt_has_few_shot_examples`
- `test_prompt_no_todos`
- `test_minimum_techniques`

### 4. Analise do README.md
Verifique se o README contem as secoes obrigatorias:
- **Tecnicas Aplicadas (Fase 2):** Justificativa e exemplos das tecnicas.
- **Resultados Finais:** Link publico do LangSmith, screenshots (ou mencao a elas) e tabela comparativa v1 vs v2.
- **Como Executar:** Instrucoes de execucao.

### Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo deve estar na branch `main`.

### 5. Logica de Aprovacao
O projeto e considerado **APROVADO** se:
- Todos os arquivos obrigatorios existem.
- O prompt `v2` demonstra aplicacao clara de pelo menos 2 tecnicas avancadas.
- Os 6 testes estao implementados no arquivo de testes.
- O README contem as 3 secoes obrigatorias com conteudo condizente.

Caso contrario, o projeto e **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida

- **Se aprovado:**
  "Seu projeto foi aprovado"

- **Se nao aprovado:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever o motivo especifico, ex: 'Faltam os testes obrigatorios no arquivo tests/test_prompts.py' ou 'O README nao contem a secao de Resultados Finais']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Entregar um software capaz de fazer pull de prompts, refatorar/otimizar, fazer push e avaliar metricas (minimo 0.9).

Tecnologias: Python 3.9+, LangChain, LangSmith, YAML.

Requisitos de Codigo:
- src/pull_prompts.py: Pull do prompt `leonanluppi/bug_to_user_story_v1`.
- prompts/bug_to_user_story_v2.yml: Prompt otimizado com pelo menos 2 tecnicas (Few-shot, CoT, Role Prompting, etc).
- src/push_prompts.py: Push do prompt v2 com metadados.
- tests/test_prompts.py: 6 testes especificos (system_prompt, role, format, few-shot, no_todos, techniques).

Criterios de Aprovacao (Metricas):
- Tone Score >= 0.9
- Acceptance Criteria Score >= 0.9
- User Story Format Score >= 0.9
- Completeness Score >= 0.9
(Analise estatica deve verificar se o aluno documentou que atingiu essas metas no README).
