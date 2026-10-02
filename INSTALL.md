# Instalar o kit · Installing the kit

[Português](#português) · [English](#english)

---

## Português

### Se você é o Claude Code e a pessoa pediu para instalar este kit
Faça exatamente isto, nesta ordem:

1. Rode no terminal, um comando de cada vez:
   ```
   claude plugin marketplace add baronglock/claudecodebr-kit
   claude plugin install kit-basico@claudecodebr
   ```
   Use o endereço `baronglock/claudecodebr-kit` mesmo que o repositório já esteja baixado numa pasta: instalado pelo endereço do GitHub, o kit continua recebendo atualizações e não depende da pasta.
2. Confira com `claude plugin list`: tem de aparecer `kit-basico@claudecodebr` com o estado `enabled`.
3. Diga à pessoa, com estas informações:
   - O kit está instalado, mas a sessão que já está aberta ainda não carregou os comandos.
   - Para carregar, ela digita `/reload-plugins` nesta sessão, ou fecha e abre o Claude Code de novo.
   - Depois disso, digitar `/kit-basico:` mostra os nove comandos. Para começar: `/kit-basico:metodo` (com a ideia dela) ou, dentro da pasta de um projeto, `/kit-basico:iniciar-projeto`.

Não instale de outro jeito: não copie arquivos para `~/.claude`, não edite `settings.json` à mão, não rode script baixado da internet. Se um dos dois comandos falhar, mostre a mensagem de erro à pessoa e pare.

Se você não tem permissão para rodar comandos no terminal, não contorne: peça à pessoa para instalar ela mesma, pelo jeito abaixo.

### Instalar à mão, dentro do Claude Code
A pessoa digita os dois comandos na sessão, um de cada vez:
```
/plugin marketplace add baronglock/claudecodebr-kit
/plugin install kit-basico@claudecodebr
```
Se o resumo da instalação terminar com «Run /reload-plugins to activate», ela digita `/reload-plugins`.

### Se os comandos não aparecerem
1. Digite `/reload-plugins`, ou feche e abra o Claude Code.
2. Os comandos têm prefixo: digite `/kit-basico:` e escolha na lista.
3. No terminal, rode `claude plugin list`. Se o `kit-basico@claudecodebr` não está na lista, repita a instalação. Se está como `disabled`, rode `claude plugin enable kit-basico@claudecodebr`.
4. Dentro do Claude Code, `/plugin` tem a aba «Errors», que diz por que um plugin não carregou.
5. Claude Code antigo: atualize com `claude update`.

### Atualizar
```
claude plugin marketplace update claudecodebr
claude plugin update kit-basico@claudecodebr
```
Depois, `/reload-plugins` na sessão aberta, ou uma sessão nova. Dentro do Claude Code também dá: `/plugin`, aba «Installed», `kit-basico`, «Update now».

### Remover
```
claude plugin uninstall kit-basico@claudecodebr
claude plugin marketplace remove claudecodebr
```

---

## English

### If you are Claude Code and the person asked you to install this kit
Do exactly this, in this order:

1. Run in the terminal, one command at a time:
   ```
   claude plugin marketplace add baronglock/claudecodebr-kit
   claude plugin install kit-basico@claudecodebr
   ```
   Use the address `baronglock/claudecodebr-kit` even if the repository is already downloaded to a folder: installed from the GitHub address, the kit keeps getting updates and does not depend on that folder.
2. Check with `claude plugin list`: it must show `kit-basico@claudecodebr` with the status `enabled`.
3. Tell the person, with this information:
   - The kit is installed, but the session that is already open has not loaded the commands yet.
   - To load them, they type `/reload-plugins` in this session, or close and reopen Claude Code.
   - After that, typing `/kit-basico:` shows the nine commands. To start: `/kit-basico:metodo` (with their idea) or, inside a project folder, `/kit-basico:iniciar-projeto`.

Do not install it any other way: do not copy files into `~/.claude`, do not edit `settings.json` by hand, do not run a script downloaded from the internet. If one of the two commands fails, show the error message to the person and stop.

If you do not have permission to run terminal commands, do not work around it: ask the person to install it themselves, as described below.

### Installing by hand, inside Claude Code
The person types the two commands in the session, one at a time:
```
/plugin marketplace add baronglock/claudecodebr-kit
/plugin install kit-basico@claudecodebr
```
If the install summary ends with "Run /reload-plugins to activate", they type `/reload-plugins`.

### If the commands do not show up
1. Type `/reload-plugins`, or close and reopen Claude Code.
2. The commands have a prefix: type `/kit-basico:` and pick from the list.
3. In the terminal, run `claude plugin list`. If `kit-basico@claudecodebr` is not listed, repeat the install. If it is `disabled`, run `claude plugin enable kit-basico@claudecodebr`.
4. Inside Claude Code, `/plugin` has an "Errors" tab that says why a plugin did not load.
5. Old Claude Code: update it with `claude update`.

### Update
```
claude plugin marketplace update claudecodebr
claude plugin update kit-basico@claudecodebr
```
Then `/reload-plugins` in the open session, or a new session. Inside Claude Code you can also use `/plugin`, the "Installed" tab, `kit-basico`, "Update now".

### Remove
```
claude plugin uninstall kit-basico@claudecodebr
claude plugin marketplace remove claudecodebr
```
