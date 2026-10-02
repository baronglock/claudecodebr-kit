# Kit básico do Claude Code BR

Cinco comandos para começar um projeto organizado no Claude Code. É o kit do grupo grátis do [@claudecodebr](https://www.instagram.com/claudecodebr) e acompanha o [curso grátis](https://curso.stauf.com.br).

**Este é o kit básico.** O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

## Instalar
Dentro do Claude Code, digite os dois comandos:

```
/plugin marketplace add baronglock/claudecodebr-kit
/plugin install kit-basico@claudecodebr
```

Precisa do Claude Code instalado e de um plano pago do Claude.

## Os cinco comandos, na ordem de uso
| comando | o que faz |
|---|---|
| `/kit-basico:iniciar-projeto` | Faz cinco perguntas e cria o `CLAUDE.md`, a memória do projeto. Também protege as tuas chaves com `.gitignore` e `.env.example`. |
| `/kit-basico:especificacao` | Entrevista você e escreve a especificação em `SPEC.md`. Não escreve código. |
| `/kit-basico:sprints` | Lê a especificação e divide o projeto em sprints com critério de pronto, em `SPRINTS.md`. |
| `/kit-basico:proximo-sprint` | Executa um sprint, mostra a prova de que funciona e marca como concluído. |
| `/kit-basico:depurar` | Recebe um erro, acha a causa, corrige e roda de novo para provar. |

Os comandos nunca apagam um arquivo que já existe: mostram o que há e perguntam.

## De onde vem
Cada comando é um dos prompts do curso grátis transformado em comando: o CLAUDE.md (Prompt 6), a injeção de contexto (Prompt 3), os sprints (Prompt 4), a construção assistida (Prompt 5) e a depuração (Prompt 7).

Quando quiser um fluxo de especificação mais completo, veja o [spec-kit](https://github.com/github/spec-kit), do GitHub.

## Atualizar e remover
- Atualizar: `/plugin`, escolha o `kit-basico` e «Update now».
- Remover: `claude plugin marketplace remove claudecodebr` no terminal.

## English
A starter kit for Claude Code: five commands that set up project memory (`CLAUDE.md`), a written spec, a sprint plan, sprint-by-sprint execution with proof, and debugging. The commands and the files they write are in Brazilian Portuguese. Install with the two commands above. Free course in English: https://curso.stauf.com.br/en/

## Aviso
Projeto independente, sem vínculo com a Anthropic. Claude e Claude Code são marcas da Anthropic.

Licença: MIT.
