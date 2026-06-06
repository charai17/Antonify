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
Your job is to receive one existing Hook node and create exactly one meaningfully different Hook variation.
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
- nodeId
- title
- purpose
- narrativeRole
- oneLineDescription
- modelReadyPrompt
- optional duration, brandContext, reference assets, and variationDirection
```

## Step 4: Define Preservation Rules

Tell the agent what must stay stable.

Example:

```text
Preserve product, audience, brand tone, duration, and narrativeRole.
```

## Step 5: Define Transformation Rules

Tell the agent what should change.

Example:

```text
Change at least three: setting, first action, camera movement, emotional angle, overlay text, pacing.
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
- a vague product
- a high-risk claims input
- a variationDirection input
- a long duration input
- a manual reference asset input

