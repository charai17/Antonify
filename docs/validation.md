# Validation

Instruction quality is proven by behavior, not by how complete the prompt looks.

## Minimum Test Set

Run every instruction through at least these cases:

1. Clear normal input
2. Vague input
3. Missing optional fields
4. Missing required field
5. Unsupported proof request
6. Manual reference asset present
7. Variation direction present
8. High-risk claims domain
9. Very short duration
10. Long duration or multi-segment duration

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

## Variation Checks

Check that a variation changes at least three meaningful dimensions and is not a paraphrase.

