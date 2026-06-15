---
name: 06-avoiding-ai-slop
description: Audit a frontend design for generic AI tells and replace them with intentional, context-specific choices
---

# Avoiding AI Slop

## Purpose

"AI slop" is the generic, cookie-cutter look that signals a design had no point of view.
Use this file to audit your own output (or existing code) and replace default choices with
intentional ones tied to the design brief.

## Activation triggers

- "This looks too generic / AI-generated / like every other site"
- "Make it more distinctive / give it character"
- A self-check pass before declaring a frontend task done.

## The tell list

### Typography tells
- Inter, Roboto, Arial, Helvetica, or raw system fonts used as the headline face by default.
- A single font for everything, with weight as the only contrast.
- No scale contrast — headings only slightly larger than body.
- The same trendy face (e.g. Space Grotesk) reused across unrelated projects.

### Color tells
- **Purple/blue/violet gradient on a white background** (the signature AI look).
- Evenly distributed multi-color palette with no dominant tone or sharp accent.
- Generic Tailwind defaults (`bg-gray-100`, `text-blue-500`) left untouched as the identity.
- Flat solid backgrounds everywhere, no atmosphere or depth.

### Layout tells
- Centered single column, hero + three feature cards + footer, every time.
- Perfectly symmetric, evenly spaced grid with no grid-breaking or focal moment.
- Rounded corners + soft shadow on every element regardless of tone.
- Predictable component patterns lifted straight from a starter template.

### Motion tells
- No motion at all, or everything fading in uniformly on a timer.
- Default linear easing.
- No standout moment; nothing rewards attention.

### Detail tells
- Emoji used as feature icons.
- Lorem ipsum or placeholder copy left in.
- Default browser focus rings removed with nothing in their place.
- Generic stock-photo hero with a dark overlay and centered white text.

## The fix — replace defaults with intent

For every tell found, make a context-specific choice:

| Generic default | Intentional replacement |
|-----------------|------------------------|
| Inter headline | A display face matched to the brief's tone |
| Purple-on-white gradient | Dominant brand tone + one sharp accent, token-driven |
| Symmetric card grid | Asymmetry, overlap, or a deliberate grid break at one moment |
| Uniform fade-in | One orchestrated, staggered page-load reveal |
| Soft shadow on everything | Shadows (or borders/none) chosen per the aesthetic |
| Flat background | Gradient mesh, grain, pattern, or layered depth that fits |

## Audit checklist

Before calling a frontend task done, confirm:

- [ ] The headline font is distinctive and intentional, not a default.
- [ ] The palette has a dominant tone and a sharp accent, driven by tokens.
- [ ] The layout has a focal point and at least one unexpected compositional choice.
- [ ] There is one memorable standout moment.
- [ ] Backgrounds have atmosphere/depth where appropriate, not just flat fills.
- [ ] No emoji-as-icons, no leftover placeholder copy, no stripped focus states.
- [ ] The design expresses the one-line brief from `01-design-thinking.md`.
- [ ] It does not look like a design you'd produce for an unrelated project.

## Reminder

Interpret creatively and make unexpected choices that feel genuinely designed for the
context. No two designs should be the same — vary themes, fonts, and aesthetics across
generations, and never converge on the "safe" common choice.
