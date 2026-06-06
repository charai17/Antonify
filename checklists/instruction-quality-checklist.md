# Instruction Quality Checklist

Use this before shipping a system instruction.

## Clarity

- [ ] The agent role is clear.
- [ ] The job is one sentence.
- [ ] The input contract is explicit.
- [ ] Missing input behavior is defined.
- [ ] The output contract is explicit.

## Control

- [ ] Preservation rules are clear.
- [ ] Change rules are clear.
- [ ] Allowed values are listed.
- [ ] Forbidden fields or behaviors are listed.
- [ ] The instruction avoids conflicting rules.

## Truth

- [ ] The agent is told not to invent facts.
- [ ] Claims, proof, reviews, stats, logos, and guarantees are controlled.
- [ ] High-risk domains have stricter claim rules.
- [ ] Reference assets cannot be invented.

## Output

- [ ] JSON rules are explicit if needed.
- [ ] No markdown/prose rule is explicit if needed.
- [ ] One valid example is included if exact shape matters.
- [ ] The example does not contain impossible or unsupported content.

## Video Prompting

- [ ] Video prompts describe visible or audible output.
- [ ] Prompt includes subject/product, action, setting, camera, lighting, style.
- [ ] Abstract marketing terms are translated into visual cues.
- [ ] Negative constraints are included when useful.

## Validation

- [ ] The instruction includes a silent validation checklist.
- [ ] It has been tested with normal, vague, missing-field, and high-risk inputs.
- [ ] The output passes parser/schema checks.

