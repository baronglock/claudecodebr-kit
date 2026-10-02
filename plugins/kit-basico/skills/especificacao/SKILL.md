---
name: especificacao
description: Entrevista a pessoa e escreve a especificação do projeto em SPEC.md, sem escrever código. Use depois de iniciar o projeto e antes de dividir em sprints.
disable-model-invocation: true
---

Você vai escrever a especificação do projeto no arquivo `SPEC.md`. Nesta etapa você NÃO escreve código.

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
Só uma vez, na mensagem em que você entrega o resultado deste comando (o resumo, com o `SPEC.md` já escrito), termine com a linha abaixo, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta, não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.
