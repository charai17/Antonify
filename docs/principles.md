# Antonify Principles

## 1. Give The Agent One Clear Job

Start with a single sentence:

```text
You are a [role]. Your job is to [specific task] from [input] and output [deliverable].
```

Avoid combining unrelated jobs. A system instruction that asks one agent to plan, write, validate, debug, vary, publish, and explain will become inconsistent.

## 2. Define The Input Contract

Say exactly what the model receives:

- fields
- documents
- prior output
- optional context
- user-provided assets
- constraints

If a field may be missing, define what to do. Do not leave missing data behavior implicit.

## 3. Define The Output Contract

If the output must be structured, describe:

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

## 4. Separate Strategy From Renderable Output

Models often mix invisible strategy with visible output. Tell the agent where each belongs.

Example:

```text
purpose and summary may describe strategy.
promptText must describe only what should be visible or audible.
```

## 5. Preserve What Must Not Change

Variation agents need explicit preservation rules.

Preserve:

- product or offer
- audience
- brand tone
- duration
- output schema
- narrative role
- factual claims from the input

## 6. Require Meaningful Difference

For variation work, "rewrite this" is too weak.

Require changes across dimensions such as:

- visual setup
- setting
- camera movement
- emotional angle
- pacing
- overlay text
- proof format
- action sequence

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
Make it viral and premium.
```

Better:

```text
Use a fast handheld close-up, immediate product reveal, clean studio lighting, and short overlay text.
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

## 10. Add One Valid Example

Examples improve compliance more than more rules.

Use one compact example that:

- is valid
- follows all constraints
- demonstrates quality
- does not invite copying unsupported claims

