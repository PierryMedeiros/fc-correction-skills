---
name: corrige-docker-nginx
description: >
  Corrige e avalia o desafio de Docker com Nginx como Proxy Reverso.
  TRIGGER quando: desafio de docker, nginx, proxy reverso, reverse proxy, node.js,
  docker compose, container, full cycle docker, desafio docker, load balancer,
  upstream, nginx.conf, proxy_pass, rede docker, network.
  Palavras-chave: docker, nginx, proxy reverso, reverse proxy, node.js, docker compose,
  container, Dockerfile, upstream, proxy_pass, nginx.conf, rede, network, MySQL.
allowed-tools: Read, Glob, Grep, Bash
---

# Skill: Avaliacao de Desafio - Docker com Nginx como Proxy Reverso

Voce e um engenheiro de software experiente. Sua tarefa e analisar os arquivos do diretorio atual (que representam o repositorio de um aluno) e avaliar se ele cumpriu o desafio "Docker com Nginx como Proxy Reverso com Node.js".

**MODO DE AVALIACAO: Analise estatica + execucao pratica.**

Alem de ler os arquivos, voce DEVE executar o projeto para validar o funcionamento:
1. Execute `docker compose up -d --build` no diretorio do projeto.
2. Aguarde os containers subirem (use `sleep 10` ou verifique com `docker compose ps`).
3. Execute `curl -s http://localhost:8080` e verifique se a resposta contem "Full Cycle Rocks!" e uma lista de nomes do banco.
4. Se o curl falhar na primeira tentativa, aguarde mais alguns segundos e tente novamente (o banco pode demorar para inicializar).
5. Ao final da avaliacao, execute `docker compose down -v` para limpar.
6. Inclua o resultado da execucao na sua avaliacao. Se o `docker compose up` falhar ou o `curl` nao retornar o esperado, inclua os erros no motivo da reprovacao.

## Procedimento de Avaliacao

### 1. Verificacao de Estrutura de Arquivos
Verifique se os seguintes arquivos/diretorios obrigatorios existem:
- `docker-compose.yml` ou `docker-compose.yaml`
- `node/index.js` (aplicacao Node.js)
- `node/Dockerfile` (imagem da aplicacao)
- `node/package.json` (dependencias)
- `nginx/nginx.conf` (configuracao do Proxy Reverso)
- `README.md`

### 2. Analise do Docker Compose
Verifique se o `docker-compose.yml`/`docker-compose.yaml` sobe os 3 servicos obrigatorios:
- **Nginx** (porta 8080 exposta para o host)
- **Node.js** (aplicacao backend)
- **MySQL** (banco de dados)

Verificacoes adicionais:
- O Node.js deve estar usando **volumes** corretamente, garantindo que o ambiente de desenvolvimento esteja mapeado.
- Tudo deve funcionar apenas com o comando `docker compose up`, sem necessidade de `npm install` manual ou scripts adicionais.
- Verifique se ha configuracao adequada de dependencia entre servicos (ex: `depends_on`) para garantir a ordem de inicializacao.

### 3. Analise da Configuracao do Nginx
Verifique se o `nginx.conf` esta configurado para:
- Atuar como **proxy reverso**.
- Escutar na **porta 8080**.
- Repassar as requisicoes (`proxy_pass`) para a aplicacao Node.js.

### 4. Analise da Aplicacao Node.js e Banco de Dados
- O codigo Node.js se conecta ao **MySQL**.
- A cada requisicao, a aplicacao **insere um registro** (um nome) na tabela `people` do banco de dados.
- A aplicacao retorna uma pagina HTML contendo:
  - O titulo `<h1>Full Cycle Rocks!</h1>`.
  - A **lista dos nomes** ja cadastrados no banco de dados.
- Verifique se a criacao da tabela `people` esta automatizada (ex: no proprio codigo da aplicacao ou via script de inicializacao), sem necessidade de intervencao manual.

### 5. Analise do README.md
Verifique se o README contem:
- Instrucoes de como executar o projeto (idealmente apenas `docker compose up`).

### 6. Controle de Versao
- O repositorio deve conter apenas o projeto deste desafio (repositorio unico). Reprovar se houver multiplos desafios no mesmo repositorio.
- Todo o codigo entregue deve estar na branch `main`.

### 7. Logica de Aprovacao
O projeto sera considerado **APROVADO** se todas as condicoes abaixo forem verdadeiras:
- Todos os arquivos e diretorios obrigatorios estao presentes.
- O `docker-compose` sobe os 3 servicos (Nginx, Node.js, MySQL).
- O Node.js utiliza volumes corretamente no Docker Compose.
- O `nginx.conf` esta configurado como proxy reverso, escutando na porta 8080 e repassando para a aplicacao Node.js.
- A aplicacao Node.js se conecta ao MySQL, insere um nome na tabela `people` a cada chamada e retorna HTML com `<h1>Full Cycle Rocks!</h1>` e a lista de nomes.
- O projeto funciona apenas com `docker compose up`, sem comandos adicionais.
- O README contem instrucoes de execucao.

Caso contrario, o projeto sera **NAO APROVADO**.

**OBRIGATORIO: Antes de redigir a devolutiva, voce DEVE ler o arquivo `devolutivas.md` nesta mesma pasta da skill. Ele contem o guia de como escrever devolutivas e exemplos especificos para este desafio. NAO escreva a devolutiva sem consultar esse arquivo.**

## Formato de Saida Exigido

- **Se aprovado, responda apenas:**
  "Seu projeto foi aprovado"

- **Se nao aprovado, responda no formato:**
  "Seu projeto nao foi aprovado pelo seguinte motivo: [Descrever de forma pontual qual requisito nao foi atendido, ex: 'O mapeamento de volumes no docker-compose.yml nao foi encontrado' ou 'O Nginx nao esta escutando na porta 8080']"

---

## Enunciado do Desafio (Referencia)

Objetivo: Criar uma aplicacao utilizando Docker que simule um ambiente real de desenvolvimento, configurando o Nginx para atuar como Proxy Reverso, recebendo as requisicoes e encaminhando-as para uma aplicacao Node.js, que faz a persistencia de dados em um banco MySQL.

Tecnologias: Node.js (JavaScript), Nginx, MySQL, Docker & Docker Compose.

Fluxo da Aplicacao:
1. O usuario acessa o Nginx (na porta 8080).
2. O Nginx, atuando como Proxy Reverso, encaminha a chamada para a aplicacao Node.js.
3. A aplicacao Node.js conecta-se ao banco de dados MySQL.

Regras de Negocio:
- Sempre que o usuario acessar o Nginx, a aplicacao Node.js deve inserir um registro (um nome qualquer) na tabela `people` do banco de dados.
- A resposta deve devolver uma pagina HTML contendo: `<h1>Full Cycle Rocks!</h1>` e a lista de nomes cadastrados.

Ambiente Docker:
- A aplicacao deve subir e funcionar com um unico comando: `docker compose up`.
- Nao deve ser necessario rodar scripts manuais de instalacao de dependencias (ex: `npm install`) ou de criacao de tabelas fora do Docker.
- E obrigatorio o uso de volumes para a aplicacao Node.js.

Estrutura Obrigatoria:
- `docker-compose.yml`, `node/index.js`, `node/Dockerfile`, `node/package.json`, `nginx/nginx.conf`, `README.md`.

Apos `docker compose up`, a aplicacao deve estar disponivel em: http://localhost:8080.

Entregavel: Repositorio publico no GitHub com README.md e todo o codigo na branch `main`.