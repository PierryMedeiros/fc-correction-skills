---
name: corrige-skills-refactor-arch
description: >
  Corrige e avalia o desafio de Criacao de Skills - Refatoracao Arquitetural Automatizada (refactor-arch).
  TRIGGER quando: desafio de criacao de skill, refactor-arch, refatoracao arquitetural, skill de refatoracao,
  MVC refactor, anti-patterns, code smells, auditoria de codigo, catalogo de anti-patterns, playbook de refatoracao,
  code-smells-project, ecommerce-api-legacy, task-manager-api, Claude Code skill, Gemini CLI skill, Codex skill.
  Palavras-chave: skill, refactor-arch, MVC, anti-pattern, code smell, auditoria, audit report, playbook,
  refatoracao, severidade, CRITICAL, HIGH, MEDIUM, LOW, God Class, hardcoded, deprecated API,
  code-smells-project, ecommerce-api-legacy, task-manager-api, SKILL.md.
allowed-tools: Read, Glob, Grep
---

# Skill: Avaliacao de Desafio - Criacao de Skills (Refatoracao Arquitetural Automatizada)

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Criacao de Skills - Refatoracao Arquitetural Automatizada".

**MODO DE AVALIACAO: Analise estatica APENAS.**

IMPORTANTE: Neste desafio voce **NAO deve executar a skill do aluno nem rodar os projetos refatorados**. O aluno ja executou a skill localmente antes de subir o repositorio — sua tarefa e avaliar o **resultado** da refatoracao e a qualidade da skill construida, nao re-executar o fluxo. Toda a avaliacao e feita lendo arquivos: SKILL.md, arquivos de referencia da skill, codigo refatorado dos 3 projetos, relatorios de auditoria e README.

Use as ferramentas Read, Glob e Grep para navegar pelo repositorio. NAO use Bash para rodar a aplicacao, a skill ou testes.

## Procedimento de Avaliacao

### 1. Verificacao da Estrutura do Repositorio
Verifique se o repositorio contem os 3 projetos-alvo e a pasta de relatorios:
- `code-smells-project/` (Python/Flask — projeto 1)
- `ecommerce-api-legacy/` (Node.js/Express — projeto 2)
- `task-manager-api/` (Python/Flask — projeto 3)
- `reports/audit-project-1.md`
- `reports/audit-project-2.md`
- `reports/audit-project-3.md`
- `README.md` na raiz

Se a ferramenta escolhida nao for Claude Code, aceite o path equivalente (ex: `.gemini/`, `.codex/`). A **convencao importa**, mas nao reprove por causa de nome de pasta desde que a skill esteja claramente organizada e o README explique.

### 2. Verificacao da Presenca da Skill nos 3 Projetos
A skill `refactor-arch` deve estar copiada dentro de cada um dos 3 projetos. No Claude Code, o path esperado e:
- `code-smells-project/.claude/skills/refactor-arch/SKILL.md`
- `ecommerce-api-legacy/.claude/skills/refactor-arch/SKILL.md`
- `task-manager-api/.claude/skills/refactor-arch/SKILL.md`

Aceite equivalente para Gemini CLI / Codex. A skill deve ser **a mesma em todos os projetos** (nao reescrita por projeto). Verifique que `SKILL.md` existe em todos os 3 locais. Se a skill so aparece em um projeto, reprovar.

### 3. Analise do SKILL.md
Leia o `SKILL.md` (basta uma das copias — devem ser identicas). Verifique:
- Contem instrucoes claras para as **3 fases sequenciais**: Fase 1 Analise, Fase 2 Auditoria, Fase 3 Refatoracao.
- A Fase 2 instrui a **pausar e pedir confirmacao** antes de modificar arquivos.
- A Fase 3 instrui a **validar o resultado** (boot da aplicacao / endpoints respondendo).
- Faz referencia aos arquivos de conhecimento (catalogo de anti-patterns, template de relatorio, playbook, guidelines MVC, heuristicas de analise).

### 4. Analise dos Arquivos de Referencia da Skill
Os arquivos de referencia (em Markdown) devem cobrir **as 5 areas de conhecimento obrigatorias**. Podem estar em um ou varios arquivos, com nomes livres, desde que o conteudo esteja presente:

| Area | O que procurar |
|---|---|
| Analise de projeto | Heuristicas para detectar linguagem, framework, banco e mapear arquitetura atual |
| Catalogo de anti-patterns | Lista de anti-patterns com sinais de deteccao + classificacao de severidade |
| Template de relatorio | Formato do audit report (Fase 2) |
| Guidelines de arquitetura MVC | Regras do padrao MVC alvo (responsabilidades de Models, Views/Routes, Controllers) |
| Playbook de refatoracao | Padroes concretos de transformacao com exemplos antes/depois |

Se alguma das 5 areas estiver ausente, reprovar.

### 5. Analise do Catalogo de Anti-Patterns
Verifique no arquivo de catalogo:
- Contem **no minimo 8 anti-patterns**.
- Severidade esta distribuida: deve haver pelo menos um CRITICAL, um HIGH, um MEDIUM e um LOW.
- Inclui **deteccao de APIs deprecated** (um dos anti-patterns deve cobrir uso de APIs obsoletas e recomendar equivalente moderno).
- Cada anti-pattern tem um sinal de deteccao concreto (nao apenas "codigo ruim").

### 6. Analise do Playbook de Refatoracao
Verifique:
- Contem **no minimo 8 padroes de transformacao**.
- Cada padrao tem **exemplo de codigo antes/depois** (blocos de codigo visiveis no Markdown).

### 7. Analise dos Relatorios de Auditoria (reports/)
Para cada um dos 3 relatorios (`audit-project-1.md`, `audit-project-2.md`, `audit-project-3.md`), verifique:
- Segue um template consistente (o mesmo definido na skill).
- Contem **no minimo 5 findings**.
- Inclui pelo menos **1 finding CRITICAL ou HIGH**.
- Cada finding tem **arquivo e linha(s)** exatos (ex: `models.py:1-350`).
- Findings ordenados por severidade (CRITICAL primeiro, LOW por ultimo) OU agrupados claramente por severidade.
- Contem um resumo (Summary) com contagem por severidade.

Se qualquer um dos 3 relatorios falhar nesses criterios, reprovar.

### 8. Analise do Codigo Refatorado (3 projetos)
Para cada projeto, verifique que a estrutura refatorada segue o **padrao MVC**:
- Existe separacao em pastas/modulos: **models**, **views** ou **routes**, **controllers**.
- Existe modulo de **configuracao** (ex: `config/` ou `settings`) — credenciais/URLs nao devem estar hardcoded no codigo principal.
- Existe **entry point claro** (ex: `app.py`, `server.js`, `index.js`, `src/app.js`) atuando como composition root.
- Existe tratamento de erros centralizado (middleware, handler, ou equivalente).

Dicas por projeto:
- **code-smells-project (Python/Flask):** estava tudo em 4 arquivos monoliticos. Apos refatoracao, deve haver `models/`, `controllers/`, `views/` (ou `routes/`) e `config/` (ou equivalente).
- **ecommerce-api-legacy (Node.js/Express):** tinha `GodManager.js`. Apos refatoracao, o God Object deve estar quebrado em modulos MVC.
- **task-manager-api (Python/Flask):** ja tinha `models/`, `routes/`, `services/`, `utils/`. Aqui a refatoracao pode ser menos drastica — aceite melhorias incrementais desde que a estrutura final esteja mais proxima de MVC e que problemas de seguranca/qualidade documentados no relatorio tenham sido corrigidos.

Verifique por amostragem se pelo menos os findings CRITICAL/HIGH do relatorio de cada projeto foram de fato aplicados no codigo (ex: se o relatorio acusa credenciais hardcoded, confirme que nao estao mais hardcoded no codigo refatorado).

**Nao rode a aplicacao.** Apenas inspecione a estrutura de diretorios e arquivos-chave.

### 9. Analise do README.md
Verifique se o README contem as 4 secoes obrigatorias:
- **A) Analise Manual:** Problemas identificados manualmente em cada um dos 3 projetos, com severidade e justificativa. Deve ter, por projeto, no minimo 5 problemas, incluindo >= 1 CRITICAL/HIGH, >= 2 MEDIUM e >= 2 LOW.
- **B) Construcao da Skill:** Decisoes de design, anti-patterns incluidos e por que, como garantiu agnosticidade de tecnologia.
- **C) Resultados:** Resumo dos findings por severidade em cada projeto, comparacao antes/depois, checklist de validacao preenchido, evidencias de que as aplicacoes rodam apos refatoracao (screenshots ou logs) e observacoes sobre o comportamento em stacks diferentes.
- **D) Como Executar:** Pre-requisitos da ferramenta escolhida e comandos de invocacao da skill em cada projeto.

### Verificacoes Adicionais
- O repositorio deve conter apenas o projeto deste desafio (nao deve ser um monorepo com outros desafios alem dos 3 projetos-alvo).
- Todo o codigo deve estar na branch `main`.
- Aceite qualquer uma das 3 ferramentas permitidas: Claude Code, Gemini CLI ou OpenAI Codex. Nao reprovar por escolha de ferramenta.

### 10. Logica de Aprovacao
O projeto sera considerado **APROVADO** se TODAS as condicoes abaixo forem verdadeiras:

**Skill:**
- `SKILL.md` existe dentro dos 3 projetos (mesma skill copiada).
- `SKILL.md` descreve as 3 fases (Analise, Auditoria com confirmacao, Refatoracao com validacao).
- Arquivos de referencia cobrem as 5 areas de conhecimento.
- Catalogo de anti-patterns tem >= 8 itens com severidade distribuida e inclui deteccao de APIs deprecated.
- Playbook de refatoracao tem >= 8 padroes com exemplos antes/depois.

**Relatorios:**
- Os 3 relatorios existem em `reports/`.
- Cada relatorio tem >= 5 findings, pelo menos 1 CRITICAL/HIGH, e cada finding referencia arquivo/linha.

**Codigo refatorado:**
- Os 3 projetos exibem estrutura MVC (models, views/routes, controllers, config, entry point).
- Pelo menos os findings CRITICAL/HIGH dos relatorios foram efetivamente corrigidos no codigo.

**README:**
- Contem as 4 secoes obrigatorias (Analise Manual, Construcao da Skill, Resultados, Como Executar).
- Analise Manual documenta >= 5 problemas por projeto com a distribuicao de severidade exigida.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O catalogo de anti-patterns contem apenas 5 itens, o enunciado exige no minimo 8 com severidade distribuida' ou 'O relatorio audit-project-2.md nao contem findings com arquivo e linha exatos']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Criar uma Skill (no Claude Code, Gemini CLI ou OpenAI Codex) capaz de analisar, auditar e refatorar qualquer projeto para o padrao MVC, de forma agnostica de tecnologia. A skill deve funcionar em 3 projetos-alvo: `code-smells-project` (Python/Flask), `ecommerce-api-legacy` (Node.js/Express) e `task-manager-api` (Python/Flask).

Ferramenta: Claude Code, Gemini CLI ou OpenAI Codex (Custom Skills).

Fases da skill (obrigatorias):
1. **Fase 1 — Analise:** Detectar stack, mapear arquitetura atual, imprimir resumo.
2. **Fase 2 — Auditoria:** Cruzar codigo contra catalogo de anti-patterns, gerar relatorio com findings (arquivo/linha, severidade CRITICAL/HIGH/MEDIUM/LOW), pedir confirmacao antes de modificar qualquer arquivo.
3. **Fase 3 — Refatoracao:** Reestruturar para MVC, validar que a aplicacao continua funcionando.

Arquivos de referencia (5 areas obrigatorias): analise de projeto, catalogo de anti-patterns, template de relatorio, guidelines MVC, playbook de refatoracao.

Requisitos da skill:
- Agnostica de tecnologia (funciona nos 3 projetos).
- Catalogo com >= 8 anti-patterns, severidade distribuida, incluindo deteccao de APIs deprecated.
- Playbook com >= 8 padroes de transformacao com exemplos antes/depois.
- Fase 2 pausa e pede confirmacao.
- Fase 3 valida boot e endpoints.

Entregavel: Repositorio publico com a skill copiada dentro dos 3 projetos, codigo refatorado dos 3 projetos, 3 relatorios em `reports/` e README com Analise Manual, Construcao da Skill, Resultados e Como Executar. Branch `main`.
