# Image Prompting

This guide turns a rough visual idea into a production-ready image-generation prompt.

Use it when writing system instructions for agents that create product images, ad stills, reference frames, thumbnails, hero images, style frames, concept art, or image-editing prompts.

## Image Prompt Goal

An image prompt should describe a single still frame clearly enough that a model can render it without hidden context.

It should answer:

- What is the subject?
- What is the subject doing, if anything?
- What is the setting?
- What is the composition?
- What is the lighting?
- What style should it use?
- What details must be accurate?
- What should not appear?

## Recommended Prompt Shape

Use this order:

1. Image type and format
2. Main subject
3. Composition and camera angle
4. Setting and background
5. Lighting
6. Materials, texture, and detail
7. Style and mood
8. Text handling, if any
9. Negative constraints

## Image Type And Format

Start with the intended output:

```text
Square product hero image, studio photography style.
```

Examples:

```text
Vertical social ad still, realistic lifestyle photography.
Wide website hero image, clean commercial product photography.
Transparent-background product cutout, sharp edges, even studio lighting.
Editorial concept art, cinematic lighting, detailed environment.
First-frame reference image for a video scene.
```

## Subject

Name the subject clearly and early.

Good:

```text
A compact black desk organizer with three pen compartments, a cable slot, and a shallow tray for sticky notes.
```

Weak:

```text
A nice office product.
```

## Composition

Composition controls how the image feels.

Useful terms:

- centered product shot
- rule-of-thirds composition
- close-up
- macro detail
- overhead flat lay
- three-quarter view
- front-facing pack shot
- low angle
- high angle
- shallow depth of field
- clean negative space
- full-bleed background
- transparent background

## Setting And Background

Make the environment concrete:

```text
Placed on a walnut desk beside a laptop, notebook, and warm desk lamp.
```

Avoid generic setting language:

```text
In a modern place.
```

## Lighting

Use visible lighting terms:

- soft diffused studio light
- natural window light
- golden hour light
- low-key lighting
- high-key lighting
- rim light
- backlight
- neon glow
- soft shadows
- crisp product highlights

## Material And Detail

For product images, describe the surface and important details:

- matte plastic
- brushed metal
- glass reflection
- fabric weave
- leather grain
- glossy label
- beveled edge
- embossed logo, only if provided
- visible scale cues

Do not invent logos, labels, certification marks, or packaging text.

## Text In Images

Text is risky in generated images. Use it only when needed.

If text is needed:

```text
Add short readable headline text: 'Desk chaos again?'
```

If text is not needed:

```text
No text, no logo, no watermark.
```

## Reference Images

Never invent reference assets.

If references exist, explain their purpose:

```text
Use reference image 1 for product shape and material.
Use reference image 2 for color palette and lighting mood.
Use reference image 3 for background style only.
```

## Image Editing Prompts

For edits, separate what must stay from what must change.

```text
Keep the product shape, camera angle, and lighting unchanged. Replace the background with a clean white studio backdrop. Remove the clutter on the desk. Do not alter the product label.
```

## Negative Constraints

Use constraints to prevent artifacts:

```text
No extra text, no watermark, no distorted hands, no fake logos, no duplicate products, no blurry product edges.
```

## Image Prompt Template

```text
[Image type and format]. [Main subject]. [Composition and camera angle]. [Setting and background]. [Lighting]. [Materials and details]. [Style and mood]. [Text instructions if any]. [Negative constraints].
```

## Example

```text
Square product hero image, realistic studio photography. A compact matte black desk organizer with three pen compartments, a cable slot, and a shallow tray for sticky notes. Centered three-quarter view on a clean walnut desk, laptop blurred softly in the background. Soft diffused studio lighting, crisp product highlights, subtle shadow under the organizer. Minimal modern workspace mood, neutral gray and warm wood color palette. No text, no fake logos, no watermark, no distorted edges.
```

