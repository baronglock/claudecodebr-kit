---
name: iniciar-projeto
description: Cria o CLAUDE.md do projeto a partir de cinco perguntas e põe a proteção básica de segredos (.gitignore e .env.example). Use no começo de um projeto.
disable-model-invocation: true
---

Você vai preparar esta pasta para um projeto organizado. Fale em português simples, sem jargão.

## 1. Olhe antes de escrever
- Liste os arquivos da pasta atual.
- Se já existe um `CLAUDE.md`, mostre o que ele tem e pergunte se a pessoa quer completar o arquivo. Nunca apague nem substitua o que já está lá.

## 2. Faça as cinco perguntas, uma de cada vez
Espere a resposta de cada uma antes de fazer a próxima. Se a pessoa disser «ainda não sei», registre assim e siga.
1. O que este projeto faz, e para quem?
2. Que tecnologias já estão decididas (frontend, backend, banco de dados, onde vai rodar)?
3. Quais são as regras do negócio que não podem ser quebradas?
4. O que você NUNCA quer que seja feito neste projeto?
5. Em que ponto o projeto está hoje?

## 3. Escreva o CLAUDE.md
Na raiz da pasta, com estas seções, preenchidas só com o que a pessoa respondeu. Não invente.

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
- Se existe um `.env`, crie `.env.example` com os NOMES das variáveis e os valores vazios. Nunca copie um valor.
- Se a pasta é um repositório git e o `.env` já foi commitado, avise com destaque: a chave precisa ser trocada.

## 5. Diga o que foi feito
Liste os arquivos criados ou alterados e diga que o próximo passo é `/kit-basico:especificacao`.

Termine a resposta com esta linha, sem mudar: «Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.»
