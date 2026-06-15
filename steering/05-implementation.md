---
name: 05-implementation
description: Implement the design in a target stack (HTML/CSS, React, Vue, Tailwind) with responsive layout and accessibility
---

# Implementation

## Purpose

Turn the locked aesthetic direction into production-grade, working code. The output must be
functional, responsive, accessible, and meticulously refined — not a static mockup.

## Before coding

- Confirm the stack. If the repo already uses a framework, match it. Read neighboring
  components first and mirror their conventions, structure, and styling approach.
- Confirm the design brief from `01-design-thinking.md` is set.
- Decide the file/component structure. Keep it minimal for skeletons; complete for the
  requested feature.

## Stack guidance

### Plain HTML / CSS / JS

- Single-file or small static set. Use modern CSS: custom properties, `clamp()`, grid,
  container queries, nesting, scroll-driven animations.
- CSS-first for motion; reach for vanilla JS only when interaction needs logic.
- No build step required — keep it portable.

### React

- Functional components and hooks. Co-locate styles (CSS Modules, styled-components, or
  Tailwind) per the project's existing approach.
- Use the **Motion** library for animation when available.
- Keep components composable; lift design tokens into a theme or CSS variables.

### Vue

- Single-file components. Use `<script setup>`. Scoped styles or the project's chosen system.
- Built-in `<Transition>`/`<TransitionGroup>` for motion; `@vueuse/motion` for richer needs.

### Tailwind

- Extend the theme (`tailwind.config`) with the project's tokens — fonts, colors, spacing —
  rather than scattering arbitrary values.
- Use `@layer` for component classes; keep utility soup readable by extracting repeated
  patterns into components.

## Responsive design

- Mobile-first. Design the small layout first, enhance upward.
- Use fluid type and space (`clamp()`) so the design scales smoothly between breakpoints.
- Prefer **container queries** for component-level responsiveness where supported.
- Test the standout moment on small screens — bold layouts must degrade gracefully.

## Accessibility (build it in, don't bolt it on)

- Semantic HTML: real `<button>`, `<nav>`, `<main>`, headings in order, `<label>` for inputs.
- Visible, well-styled focus states — never `outline: none` without a replacement.
- Color contrast meets WCAG AA (4.5:1 body, 3:1 large/UI). Don't signal state by color alone.
- `alt` text for meaningful images; `aria-hidden` for decorative ones.
- Keyboard operable: logical tab order, escape to close, focus traps for modals.
- Honor `prefers-reduced-motion` (see `04-motion-and-animation.md`).
- Full WCAG validation requires manual testing with assistive tech and expert review; the
  above is the baseline, not a guarantee.

## Quality bar before "done"

- Every state designed: hover, focus, active, disabled, loading, empty, error.
- No layout shift from late-loading fonts or images.
- Spacing and alignment are deliberate and consistent (token-based).
- The standout moment lands and the brief is visibly expressed.

## Verify

- Run the project's build/dev command and confirm it compiles with no errors.
- For React/Vue/Tailwind, run the linter/type-checker if present and fix issues.
- Open the result and sanity-check responsive behavior and the key interaction.
- Clean up any temporary files created while testing.

## Anti-patterns

- Introducing a new framework or styling system when the repo already has one.
- Pixel-perfect desktop that collapses on mobile.
- `outline: none` with no visible focus replacement.
- Shipping unstyled default states (raw focus rings removed, no hover, no empty state).
