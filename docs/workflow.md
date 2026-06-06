# Instruction Creation Workflow

Use this workflow when creating or improving a system instruction.

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
Your job is to receive a rough system instruction and rewrite it into a clearer production-ready instruction.
```

Weak:

```text
Your job is to make better prompts.
```

## Step 3: Define Input Fields

List required and optional fields.

Example:

```text
You receive:
- currentInstruction
- targetUseCase
- desiredOutputFormat
- constraints
- optional schema
- optional examples of bad outputs
```

## Step 4: Define Preservation Rules

Tell the agent what must stay stable.

Example:

```text
Preserve the user's intent, required output shape, explicit constraints, and any provided schema.
```

## Step 5: Define Transformation Rules

Tell the agent what should change.

Example:

```text
Clarify vague rules, remove duplicates, resolve conflicts, and add missing output requirements.
```

## Step 6: Define Quality Rules

Write criteria that can be checked.

Good:

```text
The first sentence must describe the opening frame, subject action, camera behavior, and immediate overlay text.
```

Weak:

```text
Make it engaging.
```

## Step 7: Define Safety And Truth Rules

Say what the agent cannot invent.

Example:

```text
Do not invent statistics, reviews, customer names, logos, guarantees, discounts, or proof.
```

## Step 8: Define Output Rules

If schema is enforced elsewhere, still say:

```text
Return only valid JSON matching the provided output schema. Do not include markdown, commentary, explanations, citations, or extra fields.
```

## Step 9: Add Validation

Add a silent pre-output checklist.

## Step 10: Test

Test with:

- a normal input
- a missing-field input
- a vague instruction
- a high-risk claims input
- a strict schema input
- a video-specific input
- an image-specific input
- a manual reference asset input
