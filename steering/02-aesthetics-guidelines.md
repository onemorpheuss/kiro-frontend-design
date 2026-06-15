---
name: 02-aesthetics-guidelines
description: Core aesthetics reference for typography, color, motion, spatial composition, and background detail
---

# Frontend Aesthetics Guidelines

## Purpose

The working reference while building. Each section is a lever to push deliberately in
service of the design brief from `01-design-thinking.md`. Pull from the deep-dive steering
files (`03`, `04`) when a section needs more depth.

## Typography

- Choose fonts that are beautiful, unique, and characterful. Avoid generic defaults (Arial,
  Inter, Roboto, system stacks) unless the brief specifically calls for system-native UI.
- Pair a distinctive **display** font with a refined, readable **body** font.
- Treat type as a design element: scale contrast, tracking, weight, and rhythm carry the
  aesthetic as much as color does.
- Deep dive → `03-typography-and-color.md`.

## Color & theme

- Commit to a cohesive palette tied to the brief. Use CSS variables (or design tokens) so
  the system stays consistent.
- **Dominant colors with sharp accents** outperform timid, evenly distributed palettes.
- Vary across generations — sometimes dark, sometimes light, sometimes a saturated
  monochrome. Never default to the same scheme every time.
- Deep dive → `03-typography-and-color.md`.

## Motion

- Use animation for impact and micro-interactions. Prioritize CSS-only solutions for plain
  HTML; use the Motion library for React when available.
- Concentrate on high-impact moments: one well-orchestrated page load with staggered reveals
  (`animation-delay`) creates more delight than scattered micro-interactions.
- Add scroll-triggered reveals and hover states that surprise.
- Deep dive → `04-motion-and-animation.md`.

## Spatial composition

- Reach for unexpected layouts: asymmetry, overlap, diagonal flow, grid-breaking elements.
- Use either generous negative space OR controlled density — choose intentionally, don't
  drift into the middle.
- Establish a clear visual hierarchy: one focal point per view, supported by everything else.
- Break the grid deliberately at moments that matter; keep it disciplined elsewhere.

## Backgrounds & visual details

Create atmosphere and depth instead of defaulting to flat solid fills. Match the technique
to the aesthetic:

- Gradient meshes and layered radial gradients
- Noise / grain overlays for texture
- Geometric patterns, dot/line grids, halftones
- Layered transparencies and depth (blur, glass)
- Dramatic, intentional shadows (long, colored, or soft)
- Decorative borders, dividers, and frames
- Custom cursors and selection styling

## Matching complexity to vision

**IMPORTANT:** Match implementation complexity to the aesthetic.

- **Maximalist** designs need elaborate code: extensive animation, layered effects, dense
  detail, custom graphics.
- **Minimalist / refined** designs need restraint and precision: careful spacing, type
  rhythm, subtle transitions, and ruthless removal of anything unnecessary.

Elegance comes from executing the vision well, not from adding more.

## The bar

Kiro is capable of extraordinary creative work. Don't hold back. Commit fully to a
distinctive vision and show what's possible when thinking outside the default.
