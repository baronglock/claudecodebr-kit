# Prompts Prontos para Copiar e Usar

*Engenharia de Prompt*

Estes são templates testados para cada etapa do processo. Copie, adapte os trechos entre `[colchetes]` e cole no Claude Code ou Gemini Deep Research.

## Prompt 1 — Pesquisa Profunda (Documento Mestre)

```
Você é um Engenheiro de Software Sênior e Especialista em Arquitetura de Nuvem. Sua tarefa é criar um documento técnico exaustivo de 15 a 25 páginas sobre o seguinte projeto:

## PROJETO: [Nome do seu projeto]

### INTENÇÃO TOTAL:
Quero construir [descreva detalhadamente o que o software faz, para quem, e que problema resolve]. O usuário final vai [descreva o fluxo completo do usuário: como entra, o que faz, o que vê, o que recebe].

### DADOS E FLUXO:
- O sistema recebe [tipo de dado de entrada]
- Processa usando [descreva a lógica/transformação desejada]
- Gera como saída [resultado esperado]
- Os dados são armazenados em [onde/como]

### REQUISITOS OBRIGATÓRIOS:
1. [Requisito funcional 1]
2. [Requisito funcional 2]
3. [Requisito funcional 3]
4. Interface [web/mobile/desktop] com design [moderno/minimalista/etc]
5. Autenticação de usuários [se aplicável]

### INSTRUÇÕES DE PESQUISA:
- Explore TODAS as tecnologias, frameworks e linguagens de programação mais efetivas e modernas do mercado atual (2025-2026) para cada componente
- Identifique as melhores APIs para cada função específica, comparando pelo menos 3 opções para cada uma
- Crie uma MATRIZ DE DECISÃO comparando cada opção em termos de: custo, latência, facilidade de implementação, documentação e estabilidade
- Deduza e complete quaisquer lacunas no meu workflow que eu possa não ter visualizado
- Inclua considerações de segurança, escalabilidade e performance
- Use cabeçalhos Markdown claros (## e ###) e tabelas comparativas obrigatoriamente
- Cite todas as fontes consultadas

### FORMATO DE SAÍDA:
Documento Markdown estruturado com:
1. Resumo Executivo
2. Arquitetura do Sistema (com diagrama textual)
3. Stack Tecnológico Recomendado (com justificativas)
4. APIs e Serviços Externos (com matriz de decisão)
5. Modelo de Dados
6. Fluxo de Telas/Interface
7. Plano de Implementação (passo a passo)
8. Estimativa de Custos de Infraestrutura
9. Riscos e Mitigações
10. Referências
```

## Prompt 2 — Refinar o Plano de Pesquisa (antes de confirmar)

```
Antes de iniciar a pesquisa, edite o plano para incluir também:

- Comparação com os seguintes competidores: [nome1, nome2, nome3]
- Análise específica de segurança para [LGPD/GDPR/autenticação OAuth]
- Verificar compatibilidade com [plataforma/serviço específico]
- Explorar opções de deploy gratuito ou de baixo custo (Vercel, Railway, Supabase, etc.)
- Incluir uma seção sobre testes automatizados e CI/CD
```

## Prompt 3 — Injeção de Contexto no Claude Code / IDE

```
Leia o arquivo PROJETO.md nesta pasta. Este é o documento de especificações completo do meu projeto.

Antes de começar a codar, me explique:
1. Como este projeto funcionará na prática (arquitetura geral)
2. Quais são os passos iniciais de implementação
3. Quais dependências precisaremos instalar
4. Qual a estrutura de pastas recomendada
5. Quais são os pontos mais críticos/complexos do projeto

Depois de me explicar, aguarde minha confirmação antes de começar a gerar código.
```

## Prompt 4 — Quebrar o Plano em Sprints (com Aprofundamento Teórico e Prático)

```
Antes de começar a codar, vamos planejar em SPRINTS incrementais.

Pegue o PROJETO.md e quebre a implementação em sprints incrementais, na ordem em que devem ser executados. Cada sprint é uma fatia coerente do produto que pode ser construída e validada de forma independente. Para CADA sprint, gere:

1. **Objetivo do sprint** — qual entrega de valor CONCRETA e demonstrável sai desse sprint (uma feature funcionando, um endpoint vivo, um fluxo testável).
2. **Aprofundamento teórico** — quais conceitos eu preciso entender ANTES de codar. Para cada conceito, escreva 1-2 parágrafos explicando o que é, por que importa nesse contexto e qual erro comum acontece quando se ignora.
3. **Aprofundamento por código** — exemplo MÍNIMO funcional do conceito-chave do sprint. Snippet rodável de verdade, não pseudocódigo. Comente cada linha não-óbvia.
4. **Tarefas técnicas** — lista numerada do que vai ser construído, em ordem de dependência. Cada tarefa é uma unidade pequena e auto-contida.
5. **Critério de Done** — checklist verificável: testes que devem passar, comportamento que deve funcionar, output esperado. Sem ambiguidade.
6. **Riscos / pegadinhas** — o que costuma dar errado nessa etapa específica e como evitar (ex: race conditions, limites de API, edge cases).
7. **Próximo passo** — o que vem depois e por que ESTE sprint precisa estar pronto antes.

Salve o resultado em SPRINTS.md na raiz do projeto. NÃO comece a codar ainda — quero revisar o plano sprint a sprint, ajustar o que fizer sentido, e depois executar um por vez.

Ao executar cada sprint, atualize SPRINTS.md marcando o sprint como concluído e registre quaisquer aprendizados ou desvios do plano original.
```

> **Por que essa técnica vira o jogo:** sem ela, o agente tende a sair codando tudo de uma vez e perde o fio em projetos médios/grandes. Quebrar em sprints força *raciocínio explícito* antes da execução, te dá pontos de revisão (você pode redirecionar antes de queimar tokens), e cria um registro vivo do projeto em SPRINTS.md que serve de mapa pra qualquer nova sessão. Use isso especialmente em projetos B2B onde cada entrega é uma reunião de stakeholder.

## Prompt 5 — Iniciar a Construção Assistida

```
Ótimo, entendi a arquitetura. Agora vamos começar a construir.

Siga exatamente o Plano de Implementação do documento PROJETO.md.
Comece pelo Passo 1: [descreva o primeiro passo do plano].

Regras:
- Crie a estrutura de pastas completa primeiro
- Instale todas as dependências necessárias
- Gere os arquivos de configuração (package.json, .env.example, etc.)
- Implemente a lógica principal seguindo o documento
- Adicione comentários explicativos no código para que eu possa aprender
- A cada etapa concluída, me diga o que foi feito e qual é o próximo passo
- Se encontrar alguma ambiguidade no documento, pergunte antes de assumir
```

## Prompt 6 — Criar Arquivo de Contexto Persistente (CLAUDE.md)

> **Atalho no Claude Code:** rode `/init`. Ele lê o projeto e gera um `CLAUDE.md` inicial. Depois use `/memory` ou o prompt abaixo para completar com decisões, regras de negócio e o status atual.

```
Crie um arquivo chamado CLAUDE.md na raiz do projeto com as seguintes informações para manter consistência entre sessões:

# Contexto do Projeto: [Nome]

## Decisões Arquiteturais
- [Listar decisões já tomadas]

## Stack Definido
- Frontend: [tecnologia]
- Backend: [tecnologia]
- Banco de Dados: [tecnologia]
- Deploy: [plataforma]

## Regras de Negócio
- [Regra 1]
- [Regra 2]

## Restrições
- [Restrição 1]
- [Restrição 2]

## Status Atual
- [x] Fase concluída
- [ ] Fase em andamento
- [ ] Próxima fase

## Notas Importantes
- [Qualquer coisa que a IA não deve esquecer entre sessões]
```

## Prompt 7 — Depuração / Debug

````
O seguinte erro apareceu ao executar [comando]:

```
[Cole a mensagem de erro completa aqui]
```

Contexto:
- Arquivo afetado: [nome do arquivo]
- O que eu estava tentando fazer: [descreva a ação]
- Último trecho de código alterado: [descreva ou cole]

Analise o erro, explique a causa raiz em linguagem simples, e corrija o código. Mostre o antes e o depois da correção.
````

## Prompt 8 — Transformar Documento em Página Web

```
Converta o conteúdo do arquivo PROJETO.md em uma página web moderna e profissional usando HTML + Tailwind CSS.

Requisitos:
- Design escuro e moderno
- Responsivo (mobile-first)
- Navegação lateral ou por seções
- Tabelas estilizadas para comparações
- Blocos de código com destaque de sintaxe
- Modo de impressão otimizado via CSS @media print
- Um único arquivo HTML autocontido (CSS inline ou via CDN)
```

> **Dica de ouro:** Defina sempre uma *persona* no início do prompt ("Você é um Engenheiro Sênior..."). Exija formato Markdown com cabeçalhos e tabelas. E se o plano parecer incompleto, edite-o ANTES de confirmar a pesquisa.

> Estes 8 prompts são o ponto de partida. No grupo grátis tem dica todo dia para ir além deles.  
> [Entrar no grupo grátis](https://curso.stauf.com.br/telegram)
