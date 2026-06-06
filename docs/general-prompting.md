# General Prompting

This guide is the provider-neutral Antonify method for writing prompts and system instructions.

Use it for any agent, not only video or image generation.

## The Core Prompt Shape

A strong prompt has five parts:

1. Role
2. Job
3. Input
4. Rules
5. Output

## Role

Tell the model what type of worker it is.

Good:

```text
You are a system-instruction editor for JSON-output AI agents.
```

Weak:

```text
You are helpful.
```

## Job

Make the job one sentence.

Good:

```text
Your job is to receive a rough system instruction, identify issues, and rewrite it into a clearer production-ready instruction.
```

Weak:

```text
Improve this.
```

## Input

List what the model receives.

Example:

```text
You receive:
- the current instruction
- the target output schema
- optional examples of bad outputs
- optional domain, style, or safety constraints
```

## Rules

Rules should be testable.

Good:

```text
Do not add fields outside the schema.
```

Weak:

```text
Be careful.
```

## Output

Define the output shape.

Example:

```text
Return exactly one revised system instruction. Do not include analysis unless requested.
```

For JSON:

```text
Return only valid JSON. Do not include markdown, prose, comments, or trailing commas.
```

## The Antonify Rewrite Pattern

When improving an instruction, do this:

1. Identify the job.
2. Identify the output format.
3. Remove duplicate rules.
4. Resolve conflicts.
5. Convert vague quality words into observable criteria.
6. Add anti-invention rules.
7. Add a validation checklist.
8. Add one valid example if exact output matters.

## Common Failure Patterns

### Too vague

```text
Make this prompt better.
```

Fix:

```text
Rewrite the prompt so it defines the role, job, input, rules, output format, and validation checklist.
```

### Too broad

```text
Write a strategy, script, shot list, JSON, API calls, and captions.
```

Fix:

```text
Output exactly one JSON object matching the schema. Do not output extra prose, API calls, or alternate formats.
```

### Too much hidden context

```text
Use our usual format.
```

Fix:

```text
Use exactly these fields: title, summary, finalInstruction.
```

### Claims drift

```text
Make the result sound proven and trusted.
```

Fix:

```text
Only use proof, statistics, reviews, testimonials, or trust signals if they are present in the input.
```

## General Prompt Template

```text
You are a [role].

Your job is to [task] from [input] and output [deliverable].

# Input

You receive:
- [field]
- [field]
- optional [field]

# Rules

- Preserve [what must stay stable].
- Change [what should change].
- Do not invent [facts, claims, assets, proof].
- If [missing information], then [fallback].

# Output

Return [format].
Do not include [forbidden output].

# Validation Before Output

Silently verify:
- output matches the format
- no unsupported facts were added
- all required fields are present
- no forbidden fields are present
- the result satisfies the job
```
