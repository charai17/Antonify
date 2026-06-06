# Antonify Method

Antonify turns a vague AI task into an operating brief the model can follow without guessing.

Default experience: the user can describe the desired agent in plain language. Antonify drafts the input schema, output schema or response pattern, and two test outputs for review.

## Core Questions

Every strong instruction answers:

- What is the agent's job?
- What input does it receive?
- What output must it produce?
- What should it preserve?
- What may it change?
- What should it avoid adding without support?
- What does a good result look like?
- How should it silently validate before answering?

## Instruction Shape

Use this order for most system instructions:

1. Role and job
2. Draft input schema or input fields
3. Output schema or response pattern
4. Preservation rules
5. Transformation rules
6. Anti-invention rules
7. Quality criteria
8. Silent validation checklist
9. Two example outputs for user review

Use `output schema` when software, automation, JSON, tables, or forms need predictable structure. Use `response pattern` when the agent is a master prompt, system instruction, writing assistant, or conversational workflow without a formal schema.

## Quality Rules

- Replace vague phrases like "make it good" with observable criteria.
- Prefer explicit allowed and forbidden behavior over broad style advice.
- Keep the instruction short enough to follow, but complete enough to remove guessing.
- Merge duplicate rules.
- Include examples only when they clarify the output shape or decision boundary.
- After creating an instruction, show two example outputs and ask the user what should change.

## JSON Agents

For strict JSON-output agents:

- State that the response must be valid JSON only.
- Define every top-level field.
- Define array item shapes.
- Say what to do when data is missing.
- Forbid invented values.
- Include one valid JSON example.

## Creative Prompt Agents

For image or video prompt agents:

- Preserve user-provided subject, product, person, brand, setting, and factual constraints.
- Separate visible scene details from camera, lighting, motion, style, and output constraints.
- Do not invent claims, text, logos, named people, or product details unless the user provides them.
- Include negative constraints only when they prevent a likely failure.

## Variation Agents

For hooks, problems, demos, proof, social proof, transformations, objections, and CTAs:

- Preserve the original claim and offer.
- Vary angle, framing, specificity, or emotional entry point.
- Do not add proof, statistics, testimonials, or guarantees that were not provided.
- Keep each variation meaningfully different.

## Skill Conversion

When turning Antonify into an agent skill:

- Make one skill per repeatable workflow.
- Put trigger terms in the description.
- Put only the core procedure in `SKILL.md`.
- Put longer examples, templates, and domain rules in `references/`.
- Add verification steps so the agent knows how to check its work.
