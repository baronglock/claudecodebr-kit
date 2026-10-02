# Do Conceito ao Produto Final

*Workflow Completo*

O fluxo completo em uma visão única:

### 1. Ter a Ideia Clara

Defina o problema, o público, o fluxo do usuário, os dados envolvidos. Não precisa ser técnico — precisa ser *preciso*.

### 2. Pesquisa Profunda (alguns minutos)

Use o **Prompt 1** no Gemini Deep Research ou Claude. Gere o Documento Mestre de 15-25 páginas. Baixe em `.md`.

### 3. Refinar o Documento

Se necessário, use o **Prompt 2** para ajustar o plano ANTES de confirmar. Adicione competidores, requisitos de segurança, etc.

### 4. Injetar no Agente de Código

Coloque o `PROJETO.md` na pasta do projeto. Use o **Prompt 3** para o agente entender tudo. Em seguida, **Prompt 4** para quebrar a execução em sprints (com teoria + código por etapa). Depois, **Prompt 5** para iniciar a construção do primeiro sprint.

### 5. Construir e Aprender

O agente gera código, instala dependências, executa testes. Você supervisiona, aprende e faz perguntas.

### 6. Depurar e Iterar

Use o **Prompt 7** para debug. Use o Canvas ou o agente para corrigir. Mantenha o `CLAUDE.md` e o `SPRINTS.md` atualizados.

### 7. Documentar e Apresentar

Use o **Prompt 8** para transformar o documento em página web profissional. Ou use MkDocs/Docusaurus para documentação navegável.

## Opções de Apresentação Final

### PDFMaker

Cole o Markdown e aplique temas profissionais com tipografia e destaque de sintaxe.

### Tailwind CSS

Peça ao agente para converter o relatório em uma página web moderna (como a do curso em curso.stauf.com.br).

### MkDocs / Docusaurus

Transforme as 25 páginas em um portal de documentação navegável com pesquisa interna e modo escuro.

> Do conceito ao produto final, ninguém precisa ir sozinho. O grupo grátis é networking de alto nível com quem também está construindo.  
> [Entrar no grupo grátis](https://curso.stauf.com.br/telegram)
