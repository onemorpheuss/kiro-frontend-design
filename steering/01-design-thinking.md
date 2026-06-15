---
name: 01-design-thinking
description: Establish purpose, audience, and a single bold aesthetic direction before writing any frontend code
---

# Design Thinking

## Purpose

Before any code, understand the context and commit to a BOLD aesthetic direction. The
quality of the final interface is decided here — a vague direction produces generic output,
a sharp one produces something memorable.

## Activation triggers

- "Build / create / design a [page, component, app, dashboard, landing page]"
- "Make this UI better / more interesting / less generic"
- "Design a [thing] for [audience/brand]"

## Step 1 — Interrogate the context

Answer these before touching code:

- **Purpose** — What problem does this interface solve? What is the primary action?
- **Audience** — Who uses it, in what environment, on what devices, how often?
- **Tone** — What should the user feel in the first three seconds?
- **Constraints** — Framework, performance budget, accessibility level, existing design system.
- **Differentiation** — What makes this UNFORGETTABLE? Name the one thing someone remembers.

If the user gave a brand, product, or audience, derive the direction from it. Don't ask a
pile of clarifying questions for a creative task — infer a strong direction and commit.

## Step 2 — Pick ONE aesthetic direction

Choose an extreme and stay true to it. Pick from these or design your own:

- Brutally minimal — Maximalist chaos — Retro-futuristic — Organic / natural
- Luxury / refined — Playful / toy-like — Editorial / magazine — Brutalist / raw
- Art deco / geometric — Soft / pastel — Industrial / utilitarian — Cyberpunk / neon
- Swiss / international — Y2K / vaporwave — Hand-drawn / sketch — Glassmorphic / spatial

The list is inspiration, not a menu. The goal is a coherent point of view, not a label.

**CRITICAL:** Intentionality, not intensity. Refined minimalism and loud maximalism both
win — what loses is a timid, in-between design with no opinion.

## Step 3 — Write a one-line design brief

Lock the direction in a single sentence before coding, e.g.:

> "Editorial fashion magazine: oversized serif display, generous whitespace, a single
> oxblood accent, asymmetric grid that breaks at section boundaries, no rounded corners."

This brief governs every later decision. If a choice doesn't serve the brief, cut it.

## Step 4 — Plan the standout moment

Decide the single highest-impact detail before implementing: a dramatic hero reveal, an
unexpected scroll interaction, a striking type treatment, a custom cursor, a textured
background. Build the rest of the design to support it, not compete with it.

## Anti-patterns

- Listing three "options" and asking the user to choose instead of committing.
- A safe, middle-of-the-road look that offends no one and excites no one.
- Borrowing the same direction (and the same trendy font) you used last time.
- Starting to code before the one-line brief exists.

## Handoff

Once the brief is set:
- Apply the core aesthetics → `02-aesthetics-guidelines.md`
- Nail fonts and color → `03-typography-and-color.md`
- Plan motion → `04-motion-and-animation.md`
- Implement in the target stack → `05-implementation.md`
