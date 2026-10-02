---
name: iniciar-projeto
description: Cria o CLAUDE.md do projeto com cinco perguntas e protege os segredos (.gitignore e .env.example). · Creates the project's CLAUDE.md from five questions and protects secrets.
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Sem nenhuma mensagem dela, siga a língua dos arquivos do projeto. Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. Os arquivos que você criar e o rodapé saem na língua dela, com os títulos das seções traduzidos.

Você vai preparar esta pasta para um projeto organizado. Fale simples, sem jargão.

## 1. Olhe antes de escrever
- Liste os arquivos da pasta atual.
- Se existe um `.env`, NÃO abra nem leia esse arquivo: ele guarda segredos. O passo 4 diz como pegar só os nomes das variáveis.
- Se já existe um `CLAUDE.md`, mostre o que ele tem e pergunte se a pessoa quer completar o arquivo. Nunca apague nem substitua o que já está lá.

## 2. Faça as cinco perguntas, uma de cada vez
Espere a resposta de cada uma antes de fazer a próxima. Se a pessoa disser «ainda não sei», registre assim e siga.
1. O que este projeto faz, e para quem?
2. Que tecnologias já estão decididas (frontend, backend, banco de dados, onde vai rodar)?
3. Quais são as regras do negócio que não podem ser quebradas?
4. O que você NUNCA quer que seja feito neste projeto?
5. Em que ponto o projeto está hoje?

## 3. Escreva o CLAUDE.md
Na raiz da pasta, com estas seções, preenchidas só com o que a pessoa respondeu. Não invente: nada de tarefa, sugestão ou solução que ela não disse. O que ela não respondeu fica como «ainda não sei». Em «Estado atual», as três linhas do modelo mostram o formato; escreva ali só o que ela respondeu na pergunta 5.

```
# Contexto do projeto: <nome>

## O que é e para quem
## Decisões já tomadas
## Stack
## Regras de negócio
## O que nunca fazer
## Estado atual
- [x] concluído
- [ ] em andamento
- [ ] próximo passo
## Como trabalhar neste projeto
- Antes de mudança grande, proponha um plano e espere aprovação.
- Antes de dizer que terminou, rode e mostre a saída.
- Se algo estiver ambíguo, pergunte antes de assumir.
```

## 4. Proteja os segredos
- Se não existe `.gitignore`, crie um com as linhas `.env`, `.env.*` e `!.env.example`. Se já existe, acrescente só as linhas que faltam.
- Se existe um `.env`, crie `.env.example` só com os NOMES das variáveis, cada um seguido de `=` e mais nada (exemplo: `API_KEY=`). Nunca copie um valor: todos ficam vazios, sem exceção, mesmo os que parecem inofensivos (porta, endereço, nome de usuário).
- Para pegar os nomes, não abra o `.env` inteiro: use um comando que mostre só o que vem antes do `=` em cada linha. Assim os valores nem entram na conversa.
- Se a pasta é um repositório git e o `.env` já foi commitado, avise com destaque: a chave precisa ser trocada.

## 5. Diga o que foi feito
Liste os arquivos criados ou alterados e diga que o próximo passo é `/kit-basico:especificacao`.

## Rodapé
Só uma vez, na mensagem em que você entrega o resultado deste comando, termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta, não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
