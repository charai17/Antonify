---
name: antonify-instruction-architect
description: Create, rewrite, or audit system instructions and reusable agent skills using the Antonify method. Use when the user asks for system prompts, agent instructions, SKILL.md files, JSON-output agents, prompt architecture, image/video prompt agents, variation agents, or validation checklists.
---

# Antonify Instruction Architect

Use this skill to turn rough intent into a precise operating brief for an AI agent.

## Inputs To Identify

- The agent's one-sentence job
- The input the agent receives
- The output the agent must produce
- The facts, claims, structure, or tone it must preserve
- The transformations it may perform
- What it must never invent
- The quality bar for a good result
- The checks it should run silently before answering

If details are missing and the task is still safe to complete, make conservative assumptions and label them.

## Workflow

1. Choose the target form: system instruction, JSON-output agent, SKILL.md, image prompt agent, video prompt agent, variation agent, or validation checklist.
2. Define the job in one sentence.
3. Write the exact input contract.
4. Write the exact output contract.
5. Add preservation rules for facts, user intent, formatting, tone, claims, brand details, or source constraints.
6. Add transformation rules that say what the agent may change, improve, restructure, classify, generate, or remove.
7. Add anti-invention rules. Make claims, proof, examples, metrics, citations, and constraints explicit.
8. Add role-specific quality criteria that are visible and testable.
9. Add a silent validation checklist.
10. Include one compact valid output example when output shape matters.

## For SKILL.md Outputs

- Use a lowercase hyphenated `name` that matches the skill folder.
- Put the most important trigger words at the start of `description`.
- Keep `SKILL.md` focused on the core workflow.
- Move deeper guidance into `references/` and mention when to read it.
- Avoid platform-specific frontmatter unless the user names a target platform.
- Prefer instructions first. Add scripts only when deterministic behavior is needed.

## Validation Checklist

Before returning, confirm:

- The agent no longer has to guess its job, input, or output.
- The output contract is specific enough to test.
- Preservation rules and allowed transformations do not conflict.
- Anti-invention rules cover unsupported facts, proof, metrics, and citations.
- The instruction says what "good" means in observable terms.
- The result is not bloated with duplicate rules.

## Reference

Use `references/antonify-method.md` for the compact Antonify method. If the full Antonify repo is available, deeper guides live in `docs/`, `templates/`, `checklists/`, and `examples/`.
