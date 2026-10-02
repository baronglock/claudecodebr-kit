---
name: especificacao
description: Entrevista você e escreve a especificação do projeto em SPEC.md, sem escrever código. · Interviews you and writes the project spec to SPEC.md, no code.
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Sem nenhuma mensagem dela, siga a língua dos arquivos do projeto. Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. Os arquivos que você criar e o rodapé saem na língua dela, com os títulos das seções traduzidos.

Você vai escrever a especificação do projeto no arquivo `SPEC.md`. Nesta etapa você NÃO escreve código. Esta é a especificação do PROJETO inteiro, feita uma vez; para cada mudança depois, o comando é `/kit-basico:spec`.

## 1. Leia o que já existe
- Leia o `CLAUDE.md`, se existir.
- Se existir um documento de pesquisa (por exemplo `PROJETO.md`, o Documento Mestre do curso), leia inteiro e pergunte só o que ele não responde.
- Se já existe um `SPEC.md`, mostre o que ele tem e pergunte se é para completar. Não substitua.

## 2. Entreviste, uma pergunta de cada vez
1. Qual é o objetivo, em uma frase?
2. Quem vai usar, e o que essa pessoa faz do começo ao fim?
3. O que entra no sistema, o que ele faz com isso, e o que sai?
4. O que é obrigatório existir na primeira versão?
5. O que fica de fora da primeira versão?
6. Como vamos saber que está pronto? Peça exemplos concretos que dê para conferir.

Se uma resposta ficar vaga, peça um exemplo. Não preencha lacuna com suposição: anote como pergunta em aberto.

## 3. Escreva o SPEC.md
```
# Especificação: <nome>

## Objetivo
## Quem usa e como
## Fluxo: entrada, processamento, saída
## Obrigatório na primeira versão
## Fora da primeira versão
## Critérios de pronto
(cada critério é uma frase que dá para conferir rodando alguma coisa)
## Perguntas em aberto
```

## 4. Mostre e confirme
Mostre o resumo da especificação e pergunte se algo está errado ou faltando. Só depois diga que o próximo passo é `/kit-basico:sprints`.

## Rodapé
Só uma vez, na mensagem em que você entrega o resultado deste comando (o resumo, com o `SPEC.md` já escrito), termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta, não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
