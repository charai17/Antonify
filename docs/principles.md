# Antonify Principles

## 1. Give The Agent One Clear Job

Start with a single sentence:

```text
You are a [role]. Your job is to [specific task] from [input] and output [deliverable].
```

Avoid combining unrelated jobs. A system instruction that asks one agent to plan, write, validate, debug, vary, publish, and explain will become inconsistent.

## 2. Draft The Input Schema

Say exactly what the model receives. If the user did not provide fields, infer the smallest useful set:

- fields
- documents
- prior output
- optional context
- user-provided assets
- constraints

If a field may be missing, define what to do. Do not leave missing data behavior implicit.

## 3. Define The Output Shape

If the output must be structured, describe a strict schema:

- top-level keys
- required fields
- allowed values
- forbidden fields
- formatting rules
- whether prose is allowed

For JSON agents, say:

```text
Output only valid JSON. Do not output markdown, prose, comments, or trailing commas.
```

If the instruction is a master prompt, system instruction, writing assistant, or conversational workflow, use a response pattern instead of a formal schema:

```text
Return a concise answer with a clear recommendation, the reasoning behind it, and any assumptions.
```

## 4. Separate Strategy From Renderable Output

Models often mix invisible strategy with visible output. Tell the agent where each belongs.

Example:

```text
purpose and summary may describe strategy.
promptText must describe only what should be visible or audible.
```

## 5. Preserve What Must Not Change

Any editing or generation agent needs explicit preservation rules.

Preserve:

- user intent
- required fields
- output schema
- factual claims from the input
- reference assets
- domain constraints
- safety constraints
- style constraints
- duration, aspect ratio, or media format when relevant

## 6. Define Transformation Scope

When the agent must improve or transform something, "rewrite this" is too weak.

Define what may change:

- wording
- structure
- missing rules
- conflicting rules
- level of detail
- visual setup
- camera movement
- composition
- lighting
- pacing

Define what must not change:

- output schema
- user's core intent
- unsupported facts
- provided references

## 7. Ban Unsupported Claims

The agent must not invent:

- statistics
- testimonials
- customer names
- logos
- guarantees
- discounts
- medical claims
- financial claims
- legal claims
- safety claims
- performance promises

When proof is missing, use visible demonstration instead of fabricated evidence.

## 8. Replace Abstract Quality Words

Weak:

```text
Make it strong and cinematic.
```

Better:

```text
Use a slow push-in from a wide shot to a close-up, soft side lighting, and a quiet focused mood.
```

## 9. Add A Silent Validation Checklist

The model should check its own output before responding.

Use a checklist like:

- output is valid JSON
- all required keys exist
- no forbidden keys exist
- allowed enum values only
- no unsupported claims
- no invented references
- final output matches the requested role

## 10. Add Two Test Examples

Examples improve compliance more than more rules. For the first user-facing draft, show two examples so the user can react.

Use two compact examples:

- is valid
- follows all constraints
- demonstrates quality
- does not invite copying unsupported claims

Use one normal example and one vague, missing-field, or edge-case example. Ask what should change before treating the instruction as final.
