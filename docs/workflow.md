# Instruction Creation Workflow

Use this workflow when creating or improving a system instruction.

The user should not have to design the input and output schema first. Antonify should infer a practical first draft, then test it with examples.

## Simple User Flow

The user can start with one sentence:

```text
Create an agent that turns messy client notes into a clear project brief.
```

Antonify should then:

1. infer the agent's job
2. draft the input schema or input fields
3. draft the output schema or response pattern
4. write the instruction
5. run two example outputs
6. ask the user what is wrong, missing, too strict, or too loose

Use `schema` for strict JSON, tables, forms, API payloads, or other structured output. Use `response pattern` for master prompts, system instructions, conversational agents, and other cases where a formal output schema would feel forced.

## Step 1: Name The Agent

Write:

```text
You are a [role] for [domain].
```

The role should describe the work, not a personality.

## Step 2: Define The Job

Write the job in one sentence.

Good:

```text
Your job is to receive rough client notes and produce a clear project brief.
```

Weak:

```text
Your job is to make things better.
```

## Step 3: Draft The Input Schema

List required and optional fields. If the user did not provide fields, infer the smallest useful set and label it as a draft.

Example:

```text
You receive:
- clientNotes
- projectGoal
- audience
- constraints
- optional deadline
- optional examples of preferred style
```

## Step 4: Draft The Output Shape

Choose one:

- strict output schema: use for JSON, tables, forms, automation payloads, or anything parsed by software
- response pattern: use for system instructions, master prompts, chat agents, writing agents, or open-ended work

Strict schema example:

```text
Return valid JSON with:
- title
- summary
- openQuestions
- nextActions
```

Response pattern example:

```text
Return:
1. A concise rewritten instruction
2. A short note naming any assumptions
3. Two example outputs for user review
```

## Step 5: Define Preservation Rules

Tell the agent what must stay stable.

Example:

```text
Preserve the user's intent, required output shape, explicit constraints, and any provided schema.
```

## Step 6: Define Transformation Rules

Tell the agent what should change.

Example:

```text
Clarify vague rules, remove duplicates, resolve conflicts, and add missing output requirements.
```

## Step 7: Define Quality Rules

Write criteria that can be checked.

Good:

```text
Every project brief must include the project goal, audience, deliverables, timeline notes, open questions, and next actions.
```

Weak:

```text
Make it useful.
```

## Step 8: Define Safety And Truth Rules

Say what the agent cannot add unless the user provided it.

Example:

```text
Do not add statistics, reviews, customer names, guarantees, discounts, or proof that the user did not provide.
```

## Step 9: Define Output Rules

If a strict schema is enforced elsewhere, still say:

```text
Return only valid JSON matching the provided output schema. Do not include markdown, commentary, explanations, citations, or extra fields.
```

If there is no strict schema, say what a good response should look like:

```text
Return a concise answer with a clear recommendation, the reasoning behind it, and any assumptions.
```

## Step 10: Add Validation

Add a silent pre-output checklist.

## Step 11: Run The Two-Example Test

After writing the instruction, produce two quick test outputs:

- Example A: a normal realistic input
- Example B: a vague, missing-field, or edge-case input

For schema-based agents, the examples should be valid outputs that match the schema.

For master prompts or open-ended agents, the examples should show the response pattern the user will actually see.

End by asking:

```text
What should change: the input fields, the output shape, the tone, the strictness, or the examples?
```

## Deeper Test Set

When the instruction is close to final, test with:

- a normal input
- a missing-field input
- a vague instruction
- a high-risk claims input
- a strict schema input
- a video-specific input
- an image-specific input
- a manual reference asset input
