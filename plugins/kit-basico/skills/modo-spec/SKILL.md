---
name: modo-spec
description: Liga o modo spec neste projeto - sem spec aprovada, o Claude não muda código. · Turns on spec mode for this project - no approved spec, no code change.
argument-hint: "[desligar | off]"
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Sem nenhuma mensagem dela, siga a língua dos arquivos do projeto. Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. Os arquivos que você criar e o rodapé saem na língua dela.

O que veio junto com o comando: $ARGUMENTS

Você vai ligar o modo spec neste projeto: uma regra, escrita no `CLAUDE.md` do projeto, que faz o Claude trabalhar por spec. É só texto. Não cria gancho, script nem trava.

## 1. Olhe
Liste a pasta. Se existe `CLAUDE.md`, leia o arquivo inteiro e veja se ele já tem as duas linhas de marcação `<!-- kit-basico:modo-spec:inicio -->` e `<!-- kit-basico:modo-spec:fim -->`.

Se a pessoa pediu para desligar: mostre o bloco que vai sair, espere o sim, remova só o bloco (com as duas marcações) e mais nada. Pare aí.

## 2. Mostre antes de gravar
Diga em poucas linhas o que vai fazer e mostre o bloco inteiro, na língua da pessoa. Pergunte se pode gravar. Não grave nada antes do sim.

Bloco em português:
```
<!-- kit-basico:modo-spec:inicio -->
## Modo spec
Antes de criar ou mudar código neste projeto, tem de existir uma spec APROVADA para essa mudança na pasta `specs/`.
- Não há spec aprovada para o que foi pedido? Pare: não escreva código. Diga em uma frase que falta a spec e proponha criá-la (com `/kit-basico:spec`, ou escrevendo `specs/NNN-nome-curto.md` no modelo de `specs/LEIA.md`). Só implemente depois que a pessoa aprovar a spec.
- Com spec aprovada: implemente só o que está nela, prove cada critério de aceite mostrando a saída e marque a spec como concluída.
- Não precisa de spec: (1) correção trivial de texto (erro de digitação, comentário, documentação); (2) a pessoa dizer «sem spec» naquele pedido; (3) trabalho pedido por um comando do kit que já tem roteiro próprio (um sprint via `/kit-basico:proximo-sprint`, a correção de um erro via `/kit-basico:depurar`).
- Ler código, explicar e investigar não precisam de spec. Mudar código precisa.
<!-- kit-basico:modo-spec:fim -->
```

Bloco em inglês:
```
<!-- kit-basico:modo-spec:inicio -->
## Spec mode
Before creating or changing code in this project, there must be an APPROVED spec for that change in the `specs/` folder.
- No approved spec for what was asked? Stop: do not write code. Say in one sentence that the spec is missing and offer to create it (with `/kit-basico:spec`, or by writing `specs/NNN-short-name.md` from the template in `specs/README.md`). Implement only after the person approves the spec.
- With an approved spec: implement only what is in it, prove each acceptance criterion by showing the output, and mark the spec as done.
- No spec needed: (1) trivial text fixes (typo, comment, documentation); (2) the person says "no spec" in that request; (3) work requested through a kit command that has its own script (a sprint via `/kit-basico:proximo-sprint`, a bug fix via `/kit-basico:depurar`).
- Reading code, explaining and investigating need no spec. Changing code does.
<!-- kit-basico:modo-spec:fim -->
```

## 3. Com o sim, grave
- `CLAUDE.md` já tem o bloco: troque só o que está entre as duas marcações. Nunca fique com dois blocos. Se já estava igual, diga isso e não mexa.
- `CLAUDE.md` existe e não tem o bloco: acrescente o bloco no fim. Não apague nem reescreva nenhuma outra linha.
- `CLAUDE.md` não existe: crie o arquivo só com o bloco e sugira `/kit-basico:iniciar-projeto` para completar o resto.
- Crie a pasta `specs/` com o arquivo `specs/LEIA.md` (em inglês, `specs/README.md`). Se o arquivo já existe, não mexa nele.

Conteúdo do `specs/LEIA.md` (traduza se a pessoa escreve em inglês):
````
# Specs deste projeto

Uma spec por mudança, um arquivo só: `NNN-nome-curto.md` (001, 002, 003...).
O estado anda assim: `rascunho` → `aprovada` → `concluída`. Só se implementa spec aprovada.
Crie com `/kit-basico:spec <ideia>` ou copie o modelo abaixo.

```
# NNN: <título curto>
Estado: rascunho
Criada em: AAAA-MM-DD

## O que muda e por quê
## Como deve se comportar
(com exemplos: «quando acontece X, o resultado é Y»)
## Fora de escopo
## Critérios de aceite
- [ ] (cada um dá para conferir rodando alguma coisa)
## Perguntas em aberto
```
````

## 4. Diga o que foi feito
Liste o que foi criado ou alterado. Diga que, daqui em diante, pedir uma mudança de código sem spec faz o Claude parar e propor a spec; que o comando para criar uma é `/kit-basico:spec`; e que para desligar basta apagar o bloco do `CLAUDE.md` (ou rodar `/kit-basico:modo-spec desligar`).

## Rodapé
Só uma vez, na mensagem em que você entrega o resultado deste comando, termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta, não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
