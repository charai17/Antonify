# Video Prompting

This guide turns a rough video idea into a production-ready video-generation prompt.

Use it when writing system instructions for agents that create `promptText`, `modelReadyPrompt`, video nodes, ad scenes, social clips, product demos, or cinematic sequences.

## Video Prompt Goal

A video prompt should describe what the model must render over time.

It should answer:

- What appears first?
- Who or what is the subject?
- What action happens?
- Where does it happen?
- How does the camera move?
- What is the lighting and style?
- What should be heard, if anything?
- What should not appear?

## Recommended Prompt Shape

Use this order:

1. Technical and style capsule
2. Subject or product
3. Action sequence
4. Environment, props, and lighting
5. Camera language
6. Visual style, color palette, texture, or rendering mode
7. Dialogue, voiceover, music, ambience, or sound effects
8. Negative constraints

## Technical And Style Capsule

Start with a compact capsule when useful:

```text
9:16 vertical ad, 24fps, 6 seconds, clean commercial product lighting.
```

Examples:

```text
16:9 cinematic product demo, natural daylight, handheld documentary feel.
9:16 UGC-style social ad, phone-camera realism, warm indoor lighting.
9:16 vertical product demo, crisp screen-recording and hand close-up style.
2.35:1 cinematic widescreen, 24fps, moody low-key lighting, slow controlled camera.
```

## Subject And Product

Name the subject early.

Good:

```text
A compact desk organizer sits on a cluttered home office desk while a person's hand searches for a missing pen.
```

Weak:

```text
Show a useful product in a relatable scene.
```

## Action Sequence

Describe visible cause and effect.

Good:

```text
The person places the organizer at the center of the desk, slides pens and cable clips into separate compartments, and clears the surface around the laptop.
```

Weak:

```text
The product makes the desk better.
```

## Camera Language

Use concrete camera terms:

- wide shot
- full shot
- medium shot
- close-up
- extreme close-up
- low angle
- high angle
- overhead
- first-person point of view
- tracking shot
- handheld follow
- slow push-in
- pull-back
- pan
- tilt
- orbit
- focus pull
- shallow depth of field
- deep focus
- quick cut feel
- slow motion
- time-lapse
- match cut
- seamless one-take movement

## Product And Advertising Moves

Use these when they fit the brief:

- product reveal
- hands-on use
- close-up detail shot
- clean pack shot
- before/after situation
- first-person usage moment
- 360-degree product rotation
- side-by-side comparison
- simple 3D exploded view
- ingredient or material detail close-up

Do not use 360 rotation, exploded views, or 3D rendering when the brief calls for realistic live action unless the user explicitly wants that style.

## Sound

Add sound only when it helps clarity or mood.

Useful sound details:

- subtle product handling sounds
- ambience
- music rhythm
- short voiceover
- natural dialogue
- button click
- page swipe
- footsteps
- fabric movement
- crowd murmur

Keep dialogue short and exact.

## Negative Constraints

End with constraints when useful:

```text
No extra captions, no subtitles, no logos, no watermarks.
```

For proof-heavy or social-proof scenes:

```text
No fake reviews, no fake numbers, no fake logos, no watermarks.
```

## Reference Assets

Never invent reference handles.

If reference assets exist, state exactly how to use them:

```text
Use @image1 for product appearance and material texture.
Use @video1 for camera movement and pacing.
Use @audio1 for music rhythm and ambience.
```

## Avoid

Do not use abstract marketing instructions as render instructions:

- make it viral
- make it premium
- build trust
- increase urgency
- make viewers care
- show high conversion
- create emotional resonance

Translate strategy into visible or audible details.

## Video Prompt Template

```text
[Technical/style capsule]. [Subject/product] [visible action sequence]. [Environment, props, and lighting]. [Camera language and pacing]. [Visual style, color, texture]. [Sound/dialogue/voiceover if useful]. [Negative constraints].
```

## Example

```text
9:16 vertical commercial ad, 24fps, 7 seconds, clean product demo lighting. A compact desk organizer is placed at the center of a cluttered home office desk. The person slides pens, sticky notes, and cable clips into separate compartments, clearing the space around the laptop. Natural daylight, practical home office setting, smooth overhead camera move into a medium product close-up, soft focus pull from scattered items to the organizer. Subtle sounds of items being placed into compartments. No captions, no logos, no watermarks, no extra text.
```

