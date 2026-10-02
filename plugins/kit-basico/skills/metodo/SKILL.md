---
name: metodo
description: Aplica o método do curso à sua ideia - monta o prompt de pesquisa profunda já preenchido. · Applies the course method to your idea - builds the deep research prompt, filled in.
argument-hint: "[sua ideia | your idea]"
disable-model-invocation: true
---

**Língua:** responda na língua em que a pessoa escreveu nesta conversa (conta o que veio junto com o comando). Sem nenhuma mensagem dela, siga a língua dos arquivos do projeto. Se a pessoa ainda não escreveu nada além do comando e nenhum arquivo do projeto indica a língua, a sua primeira mensagem sai nas DUAS línguas, curta: primeiro em português, depois em inglês. Sem pista, nunca escolha uma língua só. Daí em diante, siga a língua da resposta dela. O prompt que você montar e o rodapé saem na língua dela.

Ideia: $ARGUMENTS

Você vai conduzir a pessoa pelo método do curso gratuito do Claude Code BR, aplicado à ideia DELA. A ideia não precisa ser um app nem um site: pode ser uma automação, uma rotina pessoal, uma planilha, uma pesquisa. Não suponha tecnologia nenhuma. Neste comando você não cria arquivo nem escreve código.

## 1. Pegue a ideia
Se a pessoa não disse a ideia, pergunte: o que ela quer tirar do papel? Se o que ela disse não dá para preencher o prompt, faça no máximo duas perguntas, uma por vez: para quem é, e o que entra e o que sai. O que ficar sem resposta vai entre `[colchetes]` para ela completar.

## 2. Monte o Prompt 1 já preenchido
Este é o Prompt 1 do curso (pesquisa profunda, o «Documento Mestre»). Preencha os colchetes com a ideia dela e entregue em um bloco de código, pronto para copiar.

Regras do preenchimento:
- Mantenha as cinco partes: intenção total, dados e fluxo, requisitos obrigatórios, instruções de pesquisa, formato de saída.
- Troque a persona da primeira linha por um especialista no assunto da ideia.
- Itens que só valem para software (interface, autenticação, stack, APIs, modelo de dados, infraestrutura) saem ou viram o equivalente do assunto, quando a ideia não é software.
- Não escolha ferramenta nem tecnologia: quem compara as opções é a pesquisa.
- Use as palavras da pessoa. Requisito, categoria, prazo ou detalhe que ela não disse fica entre `[colchetes]` para ela completar, mesmo que pareça óbvio. Não invente.

Prompt 1 em português:
````
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
````

Prompt 1 em inglês:
````
You are a Senior Software Engineer and Cloud Architecture Specialist. Your task is to create an exhaustive technical document of 15 to 25 pages about the following project:

## PROJECT: [Name of your project]

### TOTAL INTENT:
I want to build [describe in detail what the software does, for whom, and what problem it solves]. The end user will [describe the complete user flow: how they get in, what they do, what they see, what they receive].

### DATA AND FLOW:
- The system receives [type of input data]
- It processes it using [describe the desired logic/transformation]
- It produces as output [expected result]
- The data is stored in [where/how]

### MANDATORY REQUIREMENTS:
1. [Functional requirement 1]
2. [Functional requirement 2]
3. [Functional requirement 3]
4. [web/mobile/desktop] interface with a [modern/minimalist/etc] design
5. User authentication [if applicable]

### RESEARCH INSTRUCTIONS:
- Explore ALL the most effective and modern technologies, frameworks and programming languages on the market today (2025-2026) for each component
- Identify the best APIs for each specific function, comparing at least 3 options for each one
- Create a DECISION MATRIX comparing each option in terms of: cost, latency, ease of implementation, documentation and stability
- Deduce and fill in any gaps in my workflow that I may not have seen
- Include security, scalability and performance considerations
- Use clear Markdown headings (## and ###) and comparison tables, without exception
- Cite all the sources consulted

### OUTPUT FORMAT:
A structured Markdown document with:
1. Executive Summary
2. System Architecture (with a text diagram)
3. Recommended Tech Stack (with justifications)
4. External APIs and Services (with a decision matrix)
5. Data Model
6. Screen/Interface Flow
7. Implementation Plan (step by step)
8. Infrastructure Cost Estimate
9. Risks and Mitigations
10. References
````

## 3. Diga o que fazer com o prompt
Em uma linha cada:
- Onde rodar: em uma ferramenta de pesquisa profunda, a que a pessoa preferir (por exemplo Gemini Deep Research ou o Claude com pesquisa).
- O que fazer com o resultado: salvar em Markdown como `PROJETO.md`, na pasta do projeto.

## 4. Mostre a ordem dos comandos do kit
1. `/kit-basico:iniciar-projeto`: cria o `CLAUDE.md`, a memória do projeto.
2. `/kit-basico:especificacao`: lê o `PROJETO.md` e escreve o `SPEC.md`.
3. `/kit-basico:sprints`: divide em sprints.
4. `/kit-basico:proximo-sprint`: executa um sprint por vez, com prova.
5. `/kit-basico:depurar`: quando aparecer um erro.
6. `/kit-basico:modo-spec` e `/kit-basico:spec`: para cada mudança depois da primeira versão.
7. `/kit-basico:gravar-metodo`: leva as regras de trabalho para todos os projetos.

O curso inteiro, com os oito prompts: https://curso.stauf.com.br (em inglês: https://curso.stauf.com.br/en/). Grupo gratuito: https://curso.stauf.com.br/telegram

## Rodapé
Só uma vez, na mensagem em que você entrega o prompt preenchido, termine com UMA das linhas abaixo: a da língua em que você respondeu, sem mudar e sem aspas. Em mensagem que só faz pergunta e espera a resposta, não ponha esta linha.

Este é o kit BÁSICO do Claude Code BR. O kit avançado faz parte do nível 2 (curso avançado + grupo VIP), que ainda vai ser lançado.

This is the BASIC kit from Claude Code BR. The advanced kit is part of level 2 (advanced course + VIP group), which hasn't launched yet.
