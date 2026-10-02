# Prompts Ready to Copy and Use

*Prompt Engineering*

These are tested templates for each stage of the process. Copy them, adapt the parts in `[brackets]` and paste them into Claude Code or Gemini Deep Research.

## Prompt 1 — Deep Research (Master Document)

```
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
```

## Prompt 2 — Refine the Research Plan (before confirming)

```
Before starting the research, edit the plan to also include:

- A comparison with the following competitors: [name1, name2, name3]
- A specific security analysis for [LGPD/GDPR/OAuth authentication]
- A compatibility check with [specific platform/service]
- An exploration of free or low-cost deploy options (Vercel, Railway, Supabase, etc.)
- A section on automated tests and CI/CD
```

## Prompt 3 — Context Injection into Claude Code / IDE

```
Read the file PROJETO.md in this folder. This is the complete specification document for my project.

Before you start coding, explain to me:
1. How this project will work in practice (overall architecture)
2. What the initial implementation steps are
3. Which dependencies we will need to install
4. What folder structure you recommend
5. What the most critical/complex points of the project are

After explaining, wait for my confirmation before you start generating code.
```

## Prompt 4 — Break the Plan into Sprints (with a Theoretical and Practical Deep Dive)

```
Before we start coding, let's plan in incremental SPRINTS.

Take PROJETO.md and break the implementation into incremental sprints, in the order in which they should be executed. Each sprint is a coherent slice of the product that can be built and validated independently. For EACH sprint, generate:

1. **Sprint goal** — which CONCRETE, demonstrable delivery of value comes out of this sprint (a working feature, a live endpoint, a testable flow).
2. **Theoretical deep dive** — which concepts I need to understand BEFORE coding. For each concept, write 1-2 paragraphs explaining what it is, why it matters in this context and which common mistake happens when it is ignored.
3. **Code deep dive** — a MINIMAL working example of the sprint's key concept. A snippet that really runs, not pseudocode. Comment every non-obvious line.
4. **Technical tasks** — a numbered list of what will be built, in order of dependency. Each task is a small, self-contained unit.
5. **Definition of Done** — a verifiable checklist: tests that must pass, behavior that must work, expected output. No ambiguity.
6. **Risks / gotchas** — what usually goes wrong at this specific stage and how to avoid it (e.g. race conditions, API limits, edge cases).
7. **Next step** — what comes next and why THIS sprint needs to be done first.

Save the result to SPRINTS.md in the project root. Do NOT start coding yet — I want to review the plan sprint by sprint, adjust whatever makes sense, and then execute one at a time.

When executing each sprint, update SPRINTS.md marking the sprint as done and record any learnings or deviations from the original plan.
```

> **Why this technique changes the game:** without it, the agent tends to start coding everything at once and loses the thread in medium/large projects. Breaking the work into sprints forces *explicit reasoning* before execution, gives you review points (you can redirect before burning tokens), and creates a living record of the project in SPRINTS.md that works as a map for any new session. Use it especially in B2B projects where every delivery is a stakeholder meeting.

## Prompt 5 — Start the Assisted Build

```
Great, I understand the architecture. Now let's start building.

Follow exactly the Implementation Plan in the PROJETO.md document.
Start with Step 1: [describe the first step of the plan].

Rules:
- Create the complete folder structure first
- Install all the necessary dependencies
- Generate the configuration files (package.json, .env.example, etc.)
- Implement the main logic following the document
- Add explanatory comments to the code so that I can learn
- After each completed step, tell me what was done and what the next step is
- If you find any ambiguity in the document, ask before assuming
```

## Prompt 6 — Create a Persistent Context File (CLAUDE.md)

> **Shortcut in Claude Code:** run `/init`. It reads the project and generates a starter `CLAUDE.md`. Then use `/memory` or the prompt below to complete it with decisions, business rules and the current status.

```
Create a file called CLAUDE.md in the project root with the following information to keep consistency between sessions:

# Project Context: [Name]

## Architectural Decisions
- [List the decisions already made]

## Defined Stack
- Frontend: [technology]
- Backend: [technology]
- Database: [technology]
- Deploy: [platform]

## Business Rules
- [Rule 1]
- [Rule 2]

## Constraints
- [Constraint 1]
- [Constraint 2]

## Current Status
- [x] Completed phase
- [ ] Phase in progress
- [ ] Next phase

## Important Notes
- [Anything the AI must not forget between sessions]
```

## Prompt 7 — Debugging

````
The following error appeared when running [command]:

```
[Paste the complete error message here]
```

Context:
- Affected file: [file name]
- What I was trying to do: [describe the action]
- Last piece of code changed: [describe or paste]

Analyze the error, explain the root cause in plain language, and fix the code. Show the before and after of the fix.
````

## Prompt 8 — Turn the Document into a Web Page

```
Convert the content of the PROJETO.md file into a modern, professional web page using HTML + Tailwind CSS.

Requirements:
- Dark, modern design
- Responsive (mobile-first)
- Side navigation or navigation by sections
- Styled tables for comparisons
- Code blocks with syntax highlighting
- Optimized print mode via CSS @media print
- A single self-contained HTML file (inline CSS or via CDN)
```

> **Golden tip:** Always define a *persona* at the start of the prompt ("You are a Senior Engineer..."). Demand Markdown format with headings and tables. And if the plan looks incomplete, edit it BEFORE confirming the research.

> These 8 prompts are the starting point. The free group has a tip every day to take them further.  
> [Join the free group · PT-BR](https://curso.stauf.com.br/telegram)
