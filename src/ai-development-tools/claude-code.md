# Claude Code

Ferramenta de programação com agente de inteligência artificial da Anthropic. Lê e entende o código do projeto, edita arquivos, executa comandos e cria commits e pull requests a partir de instruções em linguagem natural. Funciona no terminal, no Visual Studio Code, no JetBrains, no aplicativo desktop e na web.

## Documentação

Clique [aqui](https://code.claude.com/docs) para ver a documentação.

## Instalação

Clique [aqui](https://code.claude.com/docs/en/setup) para fazer a instalação.

Instalar no macOS, Linux e WSL:

```
curl -fsSL https://claude.ai/install.sh | bash
```

Instalar no Windows (PowerShell):

```
irm https://claude.ai/install.ps1 | iex
```

Ou pelo npm (requer Node.js 22 ou superior):

```
npm install -g @anthropic-ai/claude-code
```

Requer uma conta Pro, Max, Team, Enterprise ou Console. O plano gratuito do Claude não inclui o Claude Code.

## Comandos do CLI

Iniciar uma sessão na pasta do projeto:

```
claude
```

Continuar a última conversa da pasta atual:

```
claude -c
```

Escolher uma conversa anterior para retomar:

```
claude -r
```

Executar uma instrução sem abrir a sessão interativa e exibir a resposta (útil em scripts e CI/CD):

```
claude -p "Explique o que este projeto faz"
```

Verificar a instalação e as configurações, sem iniciar uma sessão:

```
claude doctor
```

Atualizar para a versão mais recente:

```
claude update
```

## Comandos da Sessão

Os comandos são digitados no início da mensagem, dentro da sessão. Digite `/` para ver todos os comandos disponíveis. Abaixo estão os mais usados.

### Configuração do Projeto

- `/init` - cria o arquivo `CLAUDE.md` com um guia do projeto (estrutura, comandos de build e teste, padrões), que o Claude lê no início de toda sessão.
- `/memory` - edita os arquivos `CLAUDE.md`, ativa ou desativa a memória automática e mostra o que foi memorizado.
- `/doctor` - faz um diagnóstico da instalação, das configurações, das extensões e do `CLAUDE.md` e propõe correções.
- `/permissions` - gerencia quais ferramentas e comandos o Claude pode usar sem pedir permissão.
- `/config` - abre as configurações (tema, modelo, estilo de saída e outras preferências).

### Contexto e Conversas

- `/clear` - inicia uma nova conversa com o contexto vazio. Use ao trocar de tarefa.
- `/compact` - resume a conversa para liberar espaço no contexto, mantendo o que é importante. Aceita instruções, ex: `/compact foque nas alterações da API`.
- `/context` - mostra o uso do contexto em um gráfico, com sugestões para economizar.
- `/resume` - retoma uma conversa anterior.
- `/rewind` - volta a conversa e/ou o código para um ponto anterior. Também pode ser acessado pressionando `Esc` duas vezes.
- `/btw` - faz uma pergunta rápida sobre a sessão sem adicioná-la à conversa.

### Modelo e Uso

- `/model` - troca o modelo de IA usado.
- `/effort` - define o nível de esforço do raciocínio (`low`, `medium`, `high`, `xhigh`, `max` ou `auto`).
- `/usage` - mostra o custo da sessão, os limites de uso do plano e estatísticas.

### Planejamento e Revisão

- `/plan` - entra no modo de planejamento, em que o Claude analisa e propõe um plano antes de alterar qualquer arquivo. Ex: `/plan corrigir o bug de autenticação`.
- `/code-review` - revisa as alterações atuais, uma branch ou um pull request em busca de bugs. Use `--fix` para aplicar as correções.
- `/security-review` - analisa as alterações da branch atual em busca de vulnerabilidades de segurança.

### Extensões

- `/mcp` - gerencia as conexões com servidores MCP.
- `/plugin` - instala, ativa e desativa plugins e marketplaces de plugins.
- `/skills` - lista as skills disponíveis e permite escondê-las do Claude.
- `/skill-doctor` - mostra quanto cada skill ocupa do contexto e com que frequência é usada, para encontrar skills que podem ser desativadas.

## Atalhos

- `Shift + Tab` - alterna entre os modos de permissão, como o normal, o de aceitar edições automaticamente e o de planejamento.
- `Esc` - interrompe o Claude. Pressionar duas vezes abre o `/rewind`.
- `!` - no início da mensagem, executa um comando no terminal sem passar pelo Claude, ex: `! npm test`.
- `@` - menciona um arquivo ou pasta para adicionar ao contexto, ex: `@src/index.ts`.

## Skills

Skills são pastas com um arquivo `SKILL.md` contendo instruções, scripts e recursos que ensinam o Claude a executar tarefas específicas. O Claude usa a skill automaticamente quando ela é relevante, ou você pode chamá-la com `/nome-da-skill`. Elas ficam em `~/.claude/skills/` (pessoais), em `.claude/skills/` (do projeto) ou são instaladas por plugins. Abaixo estão algumas das mais usadas.

### Skills do Matt Pocock

Coleção de skills para engenharia de software. A mais conhecida é a `grill-me`, que entrevista você sobre um plano ou design, uma pergunta por vez e com uma resposta recomendada, até resolver todas as decisões antes de escrever código.

Outras skills da coleção:

- `grill-with-docs` - versão da `grill-me` para engenharia, que também monta um glossário do domínio e registra as decisões de arquitetura (ADRs).
- `tdd` - desenvolvimento guiado por testes com o ciclo red-green-refactor.
- `diagnosing-bugs` - investigação em etapas de bugs difíceis e regressões de performance.

Instalação:

```
claude plugin install mattpocock-skills@claude-plugins-official
```

Depois, execute `/setup-matt-pocock-skills` uma vez em cada repositório.

Clique [aqui](https://github.com/mattpocock/skills) para ver a documentação.

### Superpowers

Framework de skills e metodologia de desenvolvimento que guia o Claude por brainstorming, planejamento, implementação com testes (TDD) e revisão de código. Inclui skills como `brainstorming`, `writing-plans`, `executing-plans`, `test-driven-development`, `systematic-debugging` e `using-git-worktrees`.

Instalação:

```
/plugin install superpowers@claude-plugins-official
```

Clique [aqui](https://github.com/obra/superpowers) para ver a documentação.

### Frontend Design

Skill oficial da Anthropic que melhora o design das interfaces geradas pelo Claude, com tipografia, hierarquia visual e estilos mais marcantes, evitando a aparência genérica. É usada automaticamente em tarefas de frontend.

Instalação:

```
/plugin install frontend-design@claude-plugins-official
```

### Skills da Anthropic

Repositório oficial da Anthropic com skills para criar e editar documentos (`docx`, `pdf`, `pptx` e `xlsx`), testar aplicações web, criar servidores MCP e criar novas skills (`skill-creator`).

Instalação:

```
/plugin marketplace add anthropics/skills
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

Clique [aqui](https://github.com/anthropics/skills) para ver a documentação.
