# Integrating Antonify as Agent Skills

Antonify fits naturally as an agent skill because it is a repeatable workflow: turn a rough intent into a clear system instruction, prompt agent, JSON-output agent, or validation checklist.

Use the included starter skill when you want an agent to apply the Antonify method automatically:

```text
skills/
`-- antonify-instruction-architect/
    |-- SKILL.md
    `-- references/
        `-- antonify-method.md
```

Copy the whole `skills/antonify-instruction-architect` folder into the skill directory for your agent. Keep the folder name and the `name` field in `SKILL.md` the same.

This repo also includes an integration-focused skill:

```text
skills/
`-- antonify-skill-integrator/
    |-- SKILL.md
    `-- references/
        `-- platform-paths.md
```

Use `antonify-instruction-architect` when the agent should create or audit instructions. Use `antonify-skill-integrator` when the agent should install Antonify into another tool, adapt skill folders, write setup docs, or verify platform skill paths.

## What To Turn Into Skills

Start with one focused skill, then split later if usage grows:

- `antonify-instruction-architect`: create, rewrite, or audit system instructions and reusable agent skills
- `antonify-skill-integrator`: install, adapt, or document Antonify across Claude Code, Codex, OpenClaw, Hermes Agent, and similar tools
- `antonify-json-agent`: design strict JSON-output agents
- `antonify-video-prompt`: create video prompt agents and video node instructions
- `antonify-image-prompt`: create image prompt and image-editing agents
- `antonify-variation-agent`: create Hook, Problem, Demo, Proof, Social Proof, Transformation, Objection, and CTA variation agents

Do not put every Antonify document into one huge `SKILL.md`. Put the core workflow in `SKILL.md`, and put deeper material in `references/` so the agent only loads it when needed.

## Claude Code

Claude Code skills live in a folder named `.claude/skills` for a project, or `~/.claude/skills` for personal skills.

Project-scoped install:

```bash
mkdir -p .claude/skills
cp -R skills/antonify-instruction-architect .claude/skills/
```

Personal install:

```bash
mkdir -p ~/.claude/skills
cp -R skills/antonify-instruction-architect ~/.claude/skills/
```

Use it directly with:

```text
/antonify-instruction-architect
```

Or ask naturally:

```text
Use Antonify to turn this rough idea into a strict system instruction.
```

Claude Code uses the skill description to decide when to load the full skill, so keep the description specific and front-loaded with trigger words such as `system instruction`, `SKILL.md`, `JSON-output agent`, and `prompt architecture`.

## Codex

Current Codex docs use `.agents/skills` for repo skills and `~/.agents/skills` for personal skills.

Repo-scoped install:

```bash
mkdir -p .agents/skills
cp -R skills/antonify-instruction-architect .agents/skills/
```

Personal install:

```bash
mkdir -p ~/.agents/skills
cp -R skills/antonify-instruction-architect ~/.agents/skills/
```

Use it explicitly by mentioning the skill:

```text
$antonify-instruction-architect
```

You can also run `/skills` in Codex CLI or IDE surfaces to check whether the skill is visible. For wider distribution in Codex, keep the skill folder as the authoring unit and package it as a Codex plugin when you want others to install it from a marketplace or repo.

## OpenClaw

OpenClaw commonly loads skills from a workspace `skills/` directory first, then from the global `~/.openclaw/skills` directory.

Workspace install:

```bash
mkdir -p /path/to/workspace/skills
cp -R /path/to/Antonify/skills/antonify-instruction-architect /path/to/workspace/skills/
```

If you are already inside this repo, the starter skill is already in the expected workspace location.

Global install:

```bash
mkdir -p ~/.openclaw/skills
cp -R skills/antonify-instruction-architect ~/.openclaw/skills/
```

Useful checks:

```bash
openclaw skills list
openclaw skills info antonify-instruction-architect
openclaw skills check
```

If OpenClaw does not pick up a changed skill, restart the gateway:

```bash
openclaw gateway restart
```

## Hermes Agent

Hermes Agent stores local skills under `~/.hermes/skills/` and can also scan additional directories through `skills.external_dirs` in `~/.hermes/config.yaml`.

Local install:

```bash
mkdir -p ~/.hermes/skills/prompting
cp -R skills/antonify-instruction-architect ~/.hermes/skills/prompting/
```

External directory option:

```yaml
skills:
  external_dirs:
    - /absolute/path/to/Antonify/skills
```

Use it directly:

```text
/antonify-instruction-architect
```

Or preload it for a session:

```bash
hermes chat -s antonify-instruction-architect -q "Create a JSON-output agent instruction for this workflow."
```

## A Portable SKILL.md Pattern

Use only the fields that travel well across agents:

```md
---
name: antonify-instruction-architect
description: Create, rewrite, or audit system instructions and reusable agent skills using the Antonify method. Use when the user asks for system prompts, agent instructions, SKILL.md files, JSON-output agents, prompt architecture, image/video prompt agents, variation agents, or validation checklists.
---

# Antonify Instruction Architect

Turn messy intent into a precise operating brief for an AI agent.

## Workflow

1. Identify the agent's job, input, output, and constraints.
2. Remove guesswork from the instruction.
3. Add preservation, transformation, and anti-invention rules.
4. Define the required output shape.
5. Add a silent validation checklist.
6. Return the finished instruction and any assumptions.
```

Avoid platform-specific fields until you are targeting one platform intentionally. For example, Claude Code and Codex support extra fields for invocation control and UI behavior, while Hermes supports Hermes-specific metadata. Those are useful, but they make the skill less portable.

## Test Prompts

Use these after installation:

```text
Use Antonify to write a system instruction for an agent that turns messy notes into strict JSON.
```

```text
Use the Antonify skill to audit this SKILL.md for unclear trigger behavior and missing validation.
```

```text
Create a role-specific variation agent for hooks. It must preserve claims and avoid inventing proof.
```

The output should have a clear job, exact input contract, exact output contract, preservation rules, anti-invention rules, and validation checks.

## Source Docs

- [Agent Skills specification](https://agentskills.io/specification)
- [Claude Code skills](https://code.claude.com/docs/en/skills)
- [Codex Agent Skills](https://developers.openai.com/codex/skills)
- [OpenClaw skills](https://openclawlab.com/en/docs/agent/skills/)
- [Hermes Agent skills](https://hermes-agent.nousresearch.com/docs/user-guide/features/skills)
