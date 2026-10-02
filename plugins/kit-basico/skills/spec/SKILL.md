---
name: spec
description: Uma spec por mudança - escreve, pede aprovação, implementa e prova. · One spec per change - writes it, asks for approval, implements and proves.
argument-hint: "[ideia da mudança | the change you want]"
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Sem nenhuma mensagem dela, siga a língua dos arquivos do projeto. Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. Os arquivos que você criar e o rodapé saem na língua dela, com os títulos das seções traduzidos.

Mudança pedida: $ARGUMENTS

Você vai cuidar de UMA mudança, do pedido até a prova, com uma spec curta em `specs/`. A `/kit-basico:especificacao` descreve o PROJETO inteiro, uma vez (`SPEC.md`); esta `spec` é para cada mudança depois.

## 1. Olhe o que já existe
Liste `specs/` (se a pasta não existe, você cria no passo 3). Leia o estado de cada spec.
- Existe spec `aprovada` e não `concluída`: retome essa. Diga qual é e vá direto ao passo 5. Se a pessoa trouxe uma ideia diferente junto com o comando, pergunte qual das duas ela quer agora.
- Existe spec em `rascunho`: mostre e peça aprovação (passo 4).

## 2. Entenda a mudança
Se a pessoa não disse o que quer mudar, pergunte. Leia só o que a mudança toca (o `CLAUDE.md`, os arquivos envolvidos).
Entrevista curta: uma pergunta por vez, e só o que falta para escrever critérios que dê para conferir. Se a ideia já está clara, não pergunte nada. O que continuar sem resposta vira «pergunta em aberto».

## 3. Escreva a spec
Um arquivo só: `specs/NNN-nome-curto.md`, com o próximo número livre (001, 002...). Curta: cabe em uma tela.
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

## 4. Peça aprovação
Mostre a spec inteira e pergunte se a pessoa aprova ou quer mudar algo. Não escreva código antes do sim. Se sobrou pergunta em aberto que muda o que vai ser construído, resolva antes de pedir aprovação.

## 5. Implemente
Com o sim, troque para `Estado: aprovada`. Implemente só o que está na spec. Se achar algo ambíguo, pare e pergunte.

## 6. Prove
Para cada critério de aceite, rode o que comprova e cole a saída na mensagem final. Se um critério não passar, conserte e rode de novo. Marque cada critério provado com `- [x]`. Não basta escrever que passou.

## 7. Feche
Troque para `Estado: concluída em AAAA-MM-DD`. Diga o que mudou e como a pessoa pode testar. Não comece outra mudança.

## Rodapé
Só uma vez, na mensagem em que você entrega o resultado deste comando (a prova do passo 6), termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta (entrevista, pedido de aprovação), não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
