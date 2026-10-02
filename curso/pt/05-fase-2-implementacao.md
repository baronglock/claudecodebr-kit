# Implementação com Agentes de IA

*Fase 2*

Com o Documento Mestre em mãos, agora você usa o **Claude Code** para transformar o texto em código real.

## Fluxo de Trabalho Passo a Passo

### 1. Configurar o Ambiente

Crie uma pasta local para o projeto. Coloque o arquivo de especificações (`PROJETO.md`) dentro dela. Abra a pasta na IDE ou terminal.

*5 min*

### 2. Injetar Contexto

Use o **Prompt 3** (em [04-prompts.md](04-prompts.md)) para que o agente leia e entenda o documento completo ANTES de começar a codar.

*Obrigatório*

### 3. Aprendizado Ativo

O agente explica a arquitetura. **Você aprende enquanto o projeto é construído.** Faça perguntas. Entenda cada decisão.

*Fase de aprendizado*

### 4. Construção Assistida

O agente gera: estrutura de pastas, arquivos de configuração, lógica principal, instala dependências e executa testes. Tudo sob sua supervisão.

*Automatizado*

### 5. Arquivo de Contexto Persistente

Rode `/init` para gerar o `CLAUDE.md` na raiz do projeto e complete com o **Prompt 6**. Isso garante que a IA nunca perca o contexto entre sessões.

*Crítico*

## Ferramentas do Agente

O agente tem acesso a ferramentas poderosas que eliminam o "copia-e-cola" (estes são os nomes oficiais no Claude Code):

### `Read`

Lê qualquer arquivo do projeto para entender o contexto.

### `Write` e `Edit`

`Write` cria ou reescreve um arquivo; `Edit` muda só o trecho certo. Você não copia nada.

### `Bash`

Executa comandos no terminal: instalar pacotes, rodar testes, iniciar servidores.

## Modo plano e subagentes

Dois recursos do Claude Code que fazem diferença desde o primeiro projeto:

### Modo plano

Aperte `Shift+Tab` até a barra de status mostrar `plan mode on` (ou digite `/plan`). O Claude lê o projeto e propõe um plano, mas não altera nenhum arquivo até você aprovar. Use antes de toda mudança grande.

### Subagentes

Peça: *«use um subagente para investigar como a autenticação funciona»*. Ele lê os arquivos no contexto dele e devolve só o resumo, e a sua conversa principal fica limpa. Para ter agentes especializados (revisor, testador), peça ao Claude para criar ou escreva em `.claude/agents/`.
