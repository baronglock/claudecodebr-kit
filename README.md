# Kit básico do Claude Code BR · Claude Code BR basic kit

[Português](#português) · [English](#english)

---

## Português

Nove comandos para trabalhar organizado no Claude Code, e o curso grátis inteiro em Markdown. É o kit do grupo grátis do [@claudecodebr](https://www.instagram.com/claudecodebr) e acompanha o [curso grátis](https://curso.stauf.com.br).

**Este é o kit básico.** O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

### Instalar
**O jeito mais fácil: peça ao teu Claude.** Cole esta frase no Claude Code:

```
Instale o kit deste repositório no meu Claude Code: https://github.com/baronglock/claudecodebr-kit
```

Quando ele terminar, digite `/reload-plugins` (ou feche e abra o Claude Code). Aí digite `/kit-basico:` e os nove comandos aparecem.

**Ou à mão**, dentro do Claude Code, um comando de cada vez:

```
/plugin marketplace add baronglock/claudecodebr-kit
/plugin install kit-basico@claudecodebr
```

Precisa do Claude Code instalado e de um plano pago do Claude. O kit é só texto: não instala script, gancho nem dependência, e não depende de nenhuma tecnologia.

**Se você é o Claude Code lendo isto** e a pessoa pediu para instalar o kit: rode no terminal `claude plugin marketplace add baronglock/claudecodebr-kit` (com esse endereço, mesmo que o repositório já esteja baixado) e depois `claude plugin install kit-basico@claudecodebr`; confira com `claude plugin list`; e diga à pessoa para digitar `/reload-plugins` ou abrir uma sessão nova, porque a sessão aberta ainda não carregou os comandos. Não instale de outro jeito. Os passos completos, o que fazer se os comandos não aparecerem, como atualizar e como remover estão em [`INSTALL.md`](INSTALL.md).

### Os comandos
| comando | o que faz |
|---|---|
| `/kit-basico:metodo` | Pega a tua ideia (app, automação, rotina, pesquisa) e monta o prompt de pesquisa profunda do curso já preenchido. |
| `/kit-basico:iniciar-projeto` | Faz cinco perguntas e cria o `CLAUDE.md`, a memória do projeto. Também protege as tuas chaves com `.gitignore` e `.env.example`. |
| `/kit-basico:especificacao` | Entrevista você e escreve a especificação do projeto em `SPEC.md`. Não escreve código. |
| `/kit-basico:sprints` | Lê a especificação e divide o projeto em sprints com critério de pronto, em `SPRINTS.md`. |
| `/kit-basico:proximo-sprint` | Executa um sprint, mostra a prova de que funciona e marca como concluído. |
| `/kit-basico:depurar` | Recebe um erro, acha a causa, corrige o mínimo e roda de novo para provar. |
| `/kit-basico:modo-spec` | Liga o modo spec no projeto: sem spec aprovada, o Claude não muda código. |
| `/kit-basico:spec` | Uma spec por mudança: escreve, pede a tua aprovação, implementa e prova. |
| `/kit-basico:gravar-metodo` | Grava as regras de trabalho do método no teu `CLAUDE.md` pessoal, para valerem em todos os projetos. |

Os comandos nunca apagam um arquivo que já existe: mostram o que há e perguntam. Eles respondem na língua em que você escrever, português ou inglês.

### Modo spec, em três linhas
1. `/kit-basico:modo-spec` grava uma regra no `CLAUDE.md` do projeto: antes de mudar código, tem de existir uma spec aprovada em `specs/`. Sem spec, o Claude para e propõe criar uma.
2. `/kit-basico:spec <ideia>` cuida de uma mudança por vez: escreve a spec curta, pede a tua aprovação, implementa, prova cada critério e marca como concluída.
3. É uma regra escrita, não uma trava: dizer «sem spec» libera aquele pedido, e apagar o bloco do `CLAUDE.md` desliga o modo.

A `especificacao` descreve o projeto inteiro, uma vez (`SPEC.md`). A `spec` é para cada mudança depois.

### O curso, dentro do repositório
O curso grátis está em [`curso/pt/`](curso/pt/README.md), em Markdown, com os oito prompts inteiros em blocos de código. Dá para usar sem instalar nada: abra o arquivo, copie o prompt e cole no teu Claude.

### De onde vem
Cada comando é um dos prompts do curso transformado em comando: a pesquisa profunda (Prompt 1), a injeção de contexto (Prompt 3), os sprints (Prompt 4), a construção assistida (Prompt 5), o `CLAUDE.md` (Prompt 6) e a depuração (Prompt 7).

Quando quiser um fluxo de especificação mais completo, veja o [spec-kit](https://github.com/github/spec-kit), do GitHub.

### Atualizar e remover
- Atualizar: no terminal, `claude plugin marketplace update claudecodebr` e depois `claude plugin update kit-basico@claudecodebr`; em seguida `/reload-plugins` ou uma sessão nova. Ou, dentro do Claude Code: `/plugin`, escolha o `kit-basico` e «Update now».
- Remover: `claude plugin marketplace remove claudecodebr` no terminal.
- Os comandos não apareceram? Veja [`INSTALL.md`](INSTALL.md).

---

## English

Nine commands for working in an organized way in Claude Code, plus the whole free course in Markdown. This is the kit of the free [@claudecodebr](https://www.instagram.com/claudecodebr) group, and it goes with the [free course](https://curso.stauf.com.br/en/).

**This is the basic kit.** The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.

### Install
**The easiest way: ask your Claude.** Paste this sentence into Claude Code:

```
Install the kit from this repository into my Claude Code: https://github.com/baronglock/claudecodebr-kit
```

When it finishes, type `/reload-plugins` (or close and reopen Claude Code). Then type `/kit-basico:` and the nine commands show up.

**Or by hand**, inside Claude Code, one command at a time:

```
/plugin marketplace add baronglock/claudecodebr-kit
/plugin install kit-basico@claudecodebr
```

You need Claude Code installed and a paid Claude plan. The kit is plain text: it installs no script, no hook and no dependency, and it does not depend on any technology.

**If you are Claude Code reading this** and the person asked you to install the kit: run `claude plugin marketplace add baronglock/claudecodebr-kit` in the terminal (with that address, even if the repository is already downloaded), then `claude plugin install kit-basico@claudecodebr`; check with `claude plugin list`; and tell the person to type `/reload-plugins` or open a new session, because the open session has not loaded the commands yet. Do not install it any other way. The full steps, what to do if the commands do not show up, how to update and how to remove are in [`INSTALL.md`](INSTALL.md).

### The commands
The command names are in Portuguese; the commands answer in the language you write in.

| command | what it does |
|---|---|
| `/kit-basico:metodo` | Takes your idea (app, automation, routine, research) and builds the course's deep research prompt, already filled in. |
| `/kit-basico:iniciar-projeto` | Asks five questions and creates `CLAUDE.md`, the project's memory. Also protects your keys with `.gitignore` and `.env.example`. |
| `/kit-basico:especificacao` | Interviews you and writes the project spec to `SPEC.md`. Writes no code. |
| `/kit-basico:sprints` | Reads the spec and splits the project into sprints with a definition of done, in `SPRINTS.md`. |
| `/kit-basico:proximo-sprint` | Runs one sprint, shows the proof that it works and marks it done. |
| `/kit-basico:depurar` | Takes an error, finds the cause, makes the smallest fix and reruns to prove it. |
| `/kit-basico:modo-spec` | Turns on spec mode for the project: no approved spec, no code change. |
| `/kit-basico:spec` | One spec per change: writes it, asks for your approval, implements and proves. |
| `/kit-basico:gravar-metodo` | Saves the method's working rules to your personal `CLAUDE.md`, so they apply to every project. |

The commands never delete a file that already exists: they show what is there and ask.

### Spec mode, in three lines
1. `/kit-basico:modo-spec` writes a rule into the project's `CLAUDE.md`: before changing code, there must be an approved spec in `specs/`. With no spec, Claude stops and offers to create one.
2. `/kit-basico:spec <idea>` handles one change at a time: it writes the short spec, asks for your approval, implements, proves each criterion and marks it done.
3. It is a written rule, not a lock: saying "no spec" lets that request through, and deleting the block from `CLAUDE.md` turns the mode off.

`especificacao` describes the whole project, once (`SPEC.md`). `spec` is for each change after that.

### The course, inside the repository
The free course is in [`curso/en/`](curso/en/README.md), in Markdown, with the eight prompts in full inside code blocks. You can use it without installing anything: open the file, copy the prompt and paste it into your Claude.

### Where it comes from
Each command is one of the course prompts turned into a command: deep research (Prompt 1), context injection (Prompt 3), sprints (Prompt 4), the assisted build (Prompt 5), `CLAUDE.md` (Prompt 6) and debugging (Prompt 7).

When you want a more complete specification flow, see GitHub's [spec-kit](https://github.com/github/spec-kit).

### Update and remove
- Update: in the terminal, `claude plugin marketplace update claudecodebr` and then `claude plugin update kit-basico@claudecodebr`; after that, `/reload-plugins` or a new session. Or, inside Claude Code: `/plugin`, choose `kit-basico` and "Update now".
- Remove: `claude plugin marketplace remove claudecodebr` in the terminal.
- Commands did not show up? See [`INSTALL.md`](INSTALL.md).

---

## Aviso · Notice
Projeto independente, sem vínculo com a Anthropic. Claude e Claude Code são marcas da Anthropic.
Independent project, not affiliated with Anthropic. Claude and Claude Code are trademarks of Anthropic.

Licença · License: MIT.
