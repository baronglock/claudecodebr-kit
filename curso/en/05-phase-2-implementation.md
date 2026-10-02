# Implementation with AI Agents

*Phase 2*

With the Master Document in hand, you now use **Claude Code** to turn the text into real code.

## Step-by-Step Workflow

### 1. Set Up the Environment

Create a local folder for the project. Put the specification file (`PROJETO.md`) inside it. Open the folder in your IDE or terminal.

*5 min*

### 2. Inject Context

Use **Prompt 3** (in [04-prompts.md](04-prompts.md)) so that the agent reads and understands the complete document BEFORE it starts coding.

*Required*

### 3. Active Learning

The agent explains the architecture. **You learn while the project is being built.** Ask questions. Understand every decision.

*Learning phase*

### 4. Assisted Build

The agent generates the folder structure, the configuration files and the main logic, installs dependencies and runs tests. All under your supervision.

*Automated*

### 5. Persistent Context File

Run `/init` to generate `CLAUDE.md` in the project root and complete it with **Prompt 6**. This ensures the AI never loses context between sessions.

*Critical*

## Agent Tools

The agent has access to powerful tools that eliminate "copy-and-paste" (these are the official names in Claude Code):

### `Read`

Reads any file in the project to understand the context.

### `Write` and `Edit`

`Write` creates or rewrites a file; `Edit` changes only the right part. You don't copy anything.

### `Bash`

Runs commands in the terminal: installing packages, running tests, starting servers.

## Plan mode and subagents

Two Claude Code features that make a difference from the very first project:

### Plan mode

Press `Shift+Tab` until the status bar shows `plan mode on` (or type `/plan`). Claude reads the project and proposes a plan, but does not change any file until you approve. Use it before every big change.

### Subagents

Ask: *"use a subagent to investigate how authentication works"*. It reads the files in its own context and returns only the summary, and your main conversation stays clean. To have specialized agents (reviewer, tester), ask Claude to create them or write them in `.claude/agents/`.
