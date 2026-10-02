---
name: gravar-metodo
description: Grava as regras de trabalho do método no seu CLAUDE.md pessoal - valem em todos os projetos. · Saves the method's working rules to your personal CLAUDE.md - they apply to every project.
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. O bloco que você gravar e o rodapé saem na língua dela.

Você vai gravar cinco regras de trabalho no `CLAUDE.md` PESSOAL da pessoa. Esse arquivo vale para todos os projetos dela nesta máquina, não só para esta pasta. Por isso: mostre antes, grave só com o sim, e nunca apague o que já está lá.

## 1. Ache o arquivo
O `CLAUDE.md` pessoal fica no diretório de configuração do Claude Code: normalmente `~/.claude/CLAUDE.md`. Se a pessoa disser que o dela fica em outro lugar, use o caminho que ela disser.
Se o arquivo existe, leia e veja se já tem as duas linhas de marcação `<!-- kit-basico:metodo:inicio -->` e `<!-- kit-basico:metodo:fim -->`. Se não conseguir ler, diga isso e siga: não grave às cegas por cima.

## 2. Mostre antes de gravar
Mostre o bloco inteiro, diga o caminho do arquivo e diga que as regras passam a valer em todos os projetos. Pergunte se pode gravar. Não grave nada antes do sim.

Bloco em português:
```
<!-- kit-basico:metodo:inicio -->
## Como eu trabalho (método Claude Code BR)
- Antes de mudança grande, proponha um plano e espere a minha aprovação.
- Antes de dizer que terminou, rode e mostre a saída. Sem saída na tela, não está pronto.
- Se algo estiver ambíguo, pergunte antes de assumir.
- Segredo (chave, senha, token) nunca vai no código: fica no `.env`, e o `.env` fica fora do git.
- Um sprint por vez: termine, prove e pare antes de começar o próximo.
<!-- kit-basico:metodo:fim -->
```

Bloco em inglês:
```
<!-- kit-basico:metodo:inicio -->
## How I work (Claude Code BR method)
- Before a big change, propose a plan and wait for my approval.
- Before saying it's done, run it and show the output. No output on screen, not done.
- If something is ambiguous, ask before assuming.
- Secrets (keys, passwords, tokens) never go in the code: they live in `.env`, and `.env` stays out of git.
- One sprint at a time: finish, prove and stop before starting the next.
<!-- kit-basico:metodo:fim -->
```

## 3. Se a pessoa disser não
Não grave nada. Diga que ela pode copiar o bloco à mão quando quiser. Termine aí.

## 4. Se a pessoa disser sim
- O arquivo já tem o bloco: troque só o que está entre as duas marcações. Nunca fique com dois blocos. Se já estava igual, diga que já estava gravado e não mexa.
- O arquivo existe e não tem o bloco: acrescente o bloco no fim, depois de uma linha em branco. Não apague nem reescreva nenhuma outra linha.
- O arquivo não existe: crie só com o bloco.
- Se a gravação for recusada (falta de permissão para escrever fora da pasta do projeto): não insista e não tente outro caminho. Diga que não gravou, mostre o bloco de novo e explique como ela mesma grava: abrir o arquivo em um editor e colar o bloco no fim, ou rodar este comando de novo e aceitar o pedido de permissão.

## 5. Diga o que foi feito
Diga o caminho do arquivo, se gravou ou não, e que para desfazer basta apagar o bloco entre as duas marcações.

## Rodapé
Só uma vez, na mensagem em que você entrega o resultado deste comando (gravou, não gravou, ou a pessoa disse não), termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta, não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
