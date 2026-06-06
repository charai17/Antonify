# Validation

Instruction quality is proven by behavior, not by how complete the prompt looks.

## Automatic Two-Example Test

After Antonify creates or rewrites an instruction, run a lightweight test before treating it as final.

Show the user:

1. Example A: a normal realistic output
2. Example B: a vague, missing-field, or edge-case output

If the instruction has a strict output schema, both examples should be valid outputs that match that schema.

If the instruction is a master prompt, system instruction, or conversational agent without a formal schema, both examples should show the proposed response pattern instead.

Then ask:

```text
What should change: the input fields, the output shape, the tone, the strictness, or the examples?
```

## Minimum Test Set

For final review, run every instruction through at least these cases:

1. Clear normal input
2. Vague input
3. Missing optional fields
4. Missing required field
5. Unsupported proof request
6. Manual reference asset present
7. Strict output schema present
8. High-risk claims domain
9. Video-specific constraints present
10. Image-specific constraints present

## JSON Agent Checks

Check:

- valid JSON parses
- no markdown wrapper
- no comments
- no trailing commas
- exact top-level fields
- no forbidden fields
- enum values are valid
- durations are numeric when required
- IDs and edge references match

## Video Prompt Checks

Check that the prompt:

- describes visible or audible output
- includes subject/product
- includes action
- includes setting
- includes camera language
- includes lighting or visual style
- includes sound/dialogue only when useful
- includes negative constraints when useful
- does not use abstract marketing intent as a render instruction
- does not invent references

## Truth Checks

Check that the output does not invent:

- statistics
- reviews
- testimonials
- customer names
- logos
- rankings
- guarantees
- urgency
- discounts
- medical/legal/financial claims

## Transformation Checks

When the instruction asks for rewriting or transformation, check that the output meaningfully improves the original instead of paraphrasing it.
