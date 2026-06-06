![Antonify hero banner](assets/antonify-hero.svg)

# Antonify

Antonify is a practical kit for creating, improving, and generalizing system instructions for AI agents, with extra image and video prompting guides.

The goal is simple: turn messy intent into instructions that give an AI model clear direction, reliable output shape, and enough judgment to do the job without drifting.

Video and image prompt guides are included as specialized extras, but the core of Antonify is generalized instruction design.

Star this repo if you want a reusable system-instruction kit for AI agents.

## Start Here: Copy The Universal Instruction Template

Use this when you want an AI agent to turn a rough idea into a clear, reusable system instruction.

```text
You are an Antonify system-instruction architect.

Your job is to turn a rough agent idea into a clear, reusable system instruction.

First, infer:
- the agent's job
- the input fields the user should provide
- whether the output needs a strict schema or a simple response pattern

Then produce:
1. the finished system instruction
2. the draft input schema
3. the draft output schema or response pattern
4. two example outputs:
   - Example A: normal realistic input
   - Example B: vague, missing-field, or edge-case input

Ask the user what feels wrong, missing, too strict, or too loose.
Revise until the instruction is clear, testable, and easy to reuse.
```

## Use Antonify In 5 Minutes

1. Copy the universal template above into Claude, ChatGPT, Codex, Claude Code, OpenClaw, Hermes Agent, or another agent tool.
2. Paste a rough request, for example: `Create an agent that turns messy client notes into project briefs.`
3. Let Antonify draft the job, input schema, output shape, rules, and validation checklist.
4. Compare the two example outputs it gives you.
5. Tell it what feels wrong, missing, too strict, or too loose.
6. Reuse the final instruction as your agent's system instruction, master prompt, or skill behavior.

## Before And After

Before:

```text
Make an agent that turns client notes into a project brief.
```

After:

```text
You are a project-brief architect.

Your job is to receive messy client notes and produce a clear project brief.

You receive:
- raw client notes
- optional business context
- optional constraints, deadline, budget, or audience

Return:
- project summary
- goals
- scope
- deliverables
- open questions
- risks or missing information

Do not invent facts, budgets, deadlines, tools, or stakeholder promises.
If information is missing, put it in open questions instead of guessing.
```

## Pick A Guide

- Start with [general system instructions](docs/general-prompting.md) for any AI agent.
- Use [image prompting](docs/image-prompting.md) for image-generation or image-editing agents.
- Use [video prompting](docs/video-prompting.md) for video-generation agents.
- Use [Agent Skill integration](docs/agent-skill-integration.md) to install Antonify in Claude Code, Codex, OpenClaw, Hermes Agent, and similar tools.

## Who This Is For

- builders creating AI agents, assistants, workflows, and skill folders
- prompt engineers turning rough ideas into reusable system instructions
- developers who need predictable JSON, table, or structured output
- creators writing image-generation or video-generation prompt agents
- teams that want instructions to be testable instead of vibes-only

## What Antonify Helps You Build

- General instruction editors and prompt architects
- System instructions for any type of AI agent
- JSON-output agents
- Workflow agents with role-specific behavior
- Validation checklists for testing whether an instruction actually works
- Extra video-generation prompt agents
- Extra image-generation and image-editing prompt agents

## Core Idea

Good system instructions are not long because they are fancy. They are complete because they answer the questions a model otherwise has to guess:

- What is my job?
- What input do I receive?
- What output must I produce?
- What should I preserve?
- What may I change?
- What does a good result look like?
- How do I silently validate before answering?

## Use Antonify As Agent Skills

Antonify can be installed as a reusable Agent Skill in tools that read `SKILL.md` folders.

This repo includes a starter skill:

```text
skills/antonify-instruction-architect/SKILL.md
```

Use it when you want Claude Code, Codex, OpenClaw, Hermes Agent, or a similar agent to create, rewrite, or audit system instructions with the Antonify method.

It also includes an integration skill:

```text
skills/antonify-skill-integrator/SKILL.md
```

Use that when you want an agent to install Antonify into another tool, adapt the folder structure, write platform-specific setup notes, or verify skill discovery paths.

Quick install map:

<img src="assets/claude-code-logo.svg" alt="Claude Code logo" width="220">

**Claude Code**

Install: copy the starter skill into `.claude/skills` or `~/.claude/skills`.

Use: `/antonify-instruction-architect`

<img src="assets/codex-skills-preview.png" alt="Codex Agent Skills preview" width="160">

**Codex**

Install: copy the starter skill into `.agents/skills` or `~/.agents/skills`.

Use: `$antonify-instruction-architect`

<img src="assets/openclaw-logo.svg" alt="OpenClaw logo" width="64">

**OpenClaw**

Install: keep it in a workspace `skills/` folder or copy it into `~/.openclaw/skills`.

Check: `openclaw skills list`

<img src="assets/hermes-agent-logo.png" alt="Hermes Agent logo" width="64">

**Hermes Agent**

Install: copy it into `~/.hermes/skills` or add this repo's `skills/` path to `skills.external_dirs`.

Use: `/antonify-instruction-architect`

See [docs/agent-skill-integration.md](docs/agent-skill-integration.md) for full install commands, test prompts, and platform notes.

## Repository Map

- [docs/principles.md](docs/principles.md): the Antonify instruction-writing principles
- [docs/workflow.md](docs/workflow.md): step-by-step workflow for creating or improving instructions
- [docs/general-prompting.md](docs/general-prompting.md): provider-neutral prompting method
- [docs/video-prompting.md](docs/video-prompting.md): direct video-generation prompt guide
- [docs/image-prompting.md](docs/image-prompting.md): direct image-generation and image-editing prompt guide
- [docs/seedance-video-prompting.md](docs/seedance-video-prompting.md): Seedance-style video prompt logic
- [docs/validation.md](docs/validation.md): how to test instructions before shipping them
- [docs/agent-skill-integration.md](docs/agent-skill-integration.md): how to install Antonify as Agent Skills in Claude Code, Codex, OpenClaw, Hermes Agent, and similar tools
- [templates/system-instruction-template.md](templates/system-instruction-template.md): general-purpose system instruction template
- [templates/json-output-agent-template.md](templates/json-output-agent-template.md): strict JSON agent template
- [templates/general-prompt-system-instruction.md](templates/general-prompt-system-instruction.md): generalized prompt architect instruction
- [templates/video-prompt-system-instruction.md](templates/video-prompt-system-instruction.md): video prompt system instruction
- [templates/image-prompt-system-instruction.md](templates/image-prompt-system-instruction.md): image prompt system instruction
- [checklists/instruction-quality-checklist.md](checklists/instruction-quality-checklist.md): practical review checklist
- [examples/system-instruction-editor.md](examples/system-instruction-editor.md): general instruction editing example
- [examples/video-prompt-agent.md](examples/video-prompt-agent.md): video prompt agent example
- [examples/image-prompt-agent.md](examples/image-prompt-agent.md): image prompt agent example
- [skills/antonify-instruction-architect/SKILL.md](skills/antonify-instruction-architect/SKILL.md): starter portable Agent Skill for applying Antonify in agent tools
- [skills/antonify-skill-integrator/SKILL.md](skills/antonify-skill-integrator/SKILL.md): starter Agent Skill for installing and adapting Antonify across agent platforms

## The Antonify Rule

If the model can fail by guessing, the instruction should remove the guess.

If the instruction repeats itself, merge the duplicate rule.

If the instruction says "make it good", replace that with visible, testable criteria.

If the output shape matters, show two examples so the user can compare and react.

## Publishing

This repo is designed to be published as `antonify`.

If GitHub CLI is installed and authenticated:

```bash
gh repo create antonify --private --source . --remote origin --push
```

Or create an empty GitHub repo named `antonify`, then run:

```bash
git remote add origin https://github.com/<your-username>/antonify.git
git push -u origin main
```

## Professional Direction

Antonify is built around one practical belief: a system instruction should behave like an operating brief for a skilled agent. It should define the job, the input, the rules, the output, and the validation path clearly enough that the model does not have to guess what "good" means.

![Antonify system instruction architecture](assets/antonify-architecture.svg)

Use Antonify when you want instructions that are:

- clear enough for a model to follow consistently
- strict enough for structured output
- flexible enough for creative work
- grounded enough to avoid invented claims
- testable enough to improve over time

The same architecture works for general agents, JSON agents, image prompt agents, and video prompt agents.

## Share Useful Examples

When sharing Antonify, show a small before/after instead of only saying the repo exists.

Useful post shape:

```text
Before: Make an agent that improves prompts.

After: Role, job, input fields, output shape, anti-invention rules, validation checklist, and two test examples.
```

Short examples are easier to understand, easier to share, and more likely to help someone star the repo because they can see the practical use immediately.

## Copy Paste Install

From a local Antonify checkout, copy both included skills into the platform you use.

Claude Code project skills:

```bash
mkdir -p .claude/skills
cp -R skills/antonify-instruction-architect .claude/skills/
cp -R skills/antonify-skill-integrator .claude/skills/
```

Codex repo skills:

```bash
mkdir -p .agents/skills
cp -R skills/antonify-instruction-architect .agents/skills/
cp -R skills/antonify-skill-integrator .agents/skills/
```

OpenClaw global skills:

```bash
mkdir -p ~/.openclaw/skills
cp -R skills/antonify-instruction-architect ~/.openclaw/skills/
cp -R skills/antonify-skill-integrator ~/.openclaw/skills/
openclaw skills list
```

Hermes Agent local skills:

```bash
mkdir -p ~/.hermes/skills
cp -R skills/antonify-instruction-architect ~/.hermes/skills/
cp -R skills/antonify-skill-integrator ~/.hermes/skills/
hermes chat -s antonify-instruction-architect -q "Create a system instruction for a strict JSON-output agent."
```
