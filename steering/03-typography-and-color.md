---
name: 03-typography-and-color
description: Choose distinctive fonts and build cohesive, token-based color systems and themes
---

# Typography & Color

## Purpose

Type and color carry most of an interface's character. Get these two right and the design
reads as intentional even before motion and layout. This file is the deep dive behind the
typography and color sections of `02-aesthetics-guidelines.md`.

## Typography

### Choosing fonts

- Pair a **display** face (headlines, hero, big moments) with a **body** face (paragraphs,
  UI text). The contrast between them is the point.
- Pick distinctive, characterful faces over safe defaults. Avoid Inter, Roboto, Arial, and
  raw system stacks unless the brief is explicitly "native OS UI."
- Match the face to the direction:
  - Editorial / luxury → high-contrast serifs (Playfair Display, Fraunces, GT Sectra feel)
  - Brutalist / raw → grotesques, monospace, oversized condensed sans
  - Retro-futuristic → geometric or wide sans, techno display faces
  - Organic / soft → humanist sans, rounded faces, warm serifs
- **Never converge.** Don't reach for the same trendy face (e.g. Space Grotesk) every time.
  Deliberately vary across projects.

### Loading fonts

- Use a reliable source (Google Fonts, Fontshare, self-hosted `@font-face`).
- Load only the weights you use. Preload the display face used above the fold.
- Always provide a sensible fallback stack to avoid layout shift.

### Type system

- Set a modular scale (e.g. 1.2–1.333 ratio) rather than arbitrary sizes.
- Push **scale contrast**: oversized headlines against small, calm body text create drama.
- Tune `line-height`, `letter-spacing`, and `font-weight` per role. Tighten tracking on
  large display text; loosen slightly on small caps/labels.
- Use `clamp()` for fluid, responsive type that scales with the viewport.

```css
:root {
  --font-display: "Fraunces", Georgia, serif;
  --font-body: "Inter Tight", system-ui, sans-serif; /* swap per brief */
  --step-0: clamp(1rem, 0.95rem + 0.3vw, 1.125rem);
  --step-4: clamp(2.5rem, 1.8rem + 3.5vw, 5rem);
}
h1 { font-family: var(--font-display); font-size: var(--step-4); letter-spacing: -0.03em; line-height: 0.95; }
body { font-family: var(--font-body); font-size: var(--step-0); line-height: 1.6; }
```

## Color

### Building the palette

- Commit to a cohesive palette derived from the brief, not a random rainbow.
- Structure it as **dominant + neutral + sharp accent**. One or two colors carry the page;
  a single accent does the pointing. Evenly distributed palettes read as timid.
- Define everything as tokens (CSS variables) so the system is consistent and themeable.
- Consider perceptual color spaces (`oklch`) for smoother, more even gradients and ramps.

```css
:root {
  --bg: #0e0b08;
  --surface: #1a1510;
  --text: #f3ece2;
  --muted: #a89a86;
  --accent: #c1440e;        /* the one sharp accent */
  --accent-soft: color-mix(in oklab, var(--accent) 18%, var(--surface));
}
```

### Themes

- Decide light vs dark intentionally per project — don't always default to one.
- If supporting both, drive them from the same tokens via `prefers-color-scheme` or a
  `data-theme` attribute, never hardcoded duplicate values.

### Contrast & accessibility

- Maintain WCAG AA contrast: 4.5:1 for body text, 3:1 for large text and meaningful UI.
- Never rely on color alone to convey state — pair it with icon, text, or shape.
- Test the accent against every surface it lands on.
- Full WCAG compliance needs manual testing with assistive tech and expert review; meeting
  contrast ratios is necessary but not sufficient.

## Anti-patterns

- Purple/blue gradient on a white background (the canonical AI-slop look).
- Five competing accent colors with no dominant tone.
- Generic body font scaled up and called a "headline."
- Hardcoded hex values scattered through components instead of tokens.
