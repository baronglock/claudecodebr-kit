---
name: proximo-sprint
description: Executa o próximo sprint, mostra a prova e marca como concluído. Um por vez. · Runs the next sprint, shows the proof and marks it done. One at a time.
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Sem nenhuma mensagem dela, siga a língua dos arquivos do projeto. Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. O que você escrever nos arquivos e o rodapé saem na língua dela.

Você vai executar UM sprint: o primeiro de `SPRINTS.md` que ainda não está concluído.

## 1. Escolha o sprint
Leia `SPRINTS.md`, `SPEC.md` e `CLAUDE.md`. Se `SPRINTS.md` não existe, diga que o passo anterior é `/kit-basico:sprints` e pare.
Diga qual sprint vai executar, repita o objetivo e o critério de pronto, e espere a pessoa confirmar.

## 2. Construa
Siga as tarefas na ordem. Explique em uma linha o que cada passo faz. Se achar algo ambíguo na especificação, pare e pergunte.

## 3. Prove
Para cada item do critério de pronto, rode o que comprova (teste, comando, chamada) e mostre a saída. Se um item não passar, conserte e rode de novo. Não diga que está pronto sem a saída na tela: na mensagem final, cole a saída de cada comando de prova. Não basta escrever que passou.

## 4. Registre
Em `SPRINTS.md`, marque o sprint como concluído com a data e escreva em poucas linhas o que foi diferente do plano. Atualize o «Estado atual» do `CLAUDE.md`.

## 5. Pare
Não comece o sprint seguinte. Diga o que ficou pronto, o que a pessoa pode testar e qual é o próximo sprint.

## Rodapé
Só uma vez, na mensagem em que você entrega o resultado deste comando (ou em que para porque falta o `SPRINTS.md`), termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas (se a mensagem saiu nas duas línguas, as duas). Em mensagem que só faz pergunta e espera a resposta (como o pedido de confirmação do passo 1), não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
