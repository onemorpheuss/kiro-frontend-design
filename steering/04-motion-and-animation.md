---
name: 04-motion-and-animation
description: Add high-impact motion, orchestrated page-load reveals, scroll interactions, and micro-interactions
---

# Motion & Animation

## Purpose

Motion turns a static layout into an experience. The goal is concentrated impact: a few
well-orchestrated moments beat dozens of scattered, fidgety transitions. This is the deep
dive behind the motion section of `02-aesthetics-guidelines.md`.

## Principles

- **Concentrate impact.** One choreographed page load with staggered reveals delights more
  than micro-interactions sprinkled everywhere.
- **Motion has meaning.** Animate to guide attention, show relationships, or reward action —
  not for decoration alone.
- **Easing matters.** Avoid linear. Use custom cubic-beziers; ease-out for entrances,
  ease-in for exits, spring-like curves for playful directions.
- **Respect speed.** UI feedback should feel instant (120–200ms). Expressive reveals can run
  longer (400–800ms) but must never block interaction.

## Tooling

- **Plain HTML/CSS** → Prioritize CSS-only solutions: `@keyframes`, `transition`,
  `animation-delay`, scroll-driven animations (`animation-timeline: view()`).
- **React** → Use the **Motion** library (`motion`/Framer Motion) when available for
  orchestration, layout animations, and gestures.
- **Vue** → Use built-in `<Transition>`/`<TransitionGroup>`, or `@vueuse/motion`.

## High-impact moment: orchestrated page load

Stagger reveals with incremental delay so the page assembles itself with intent:

```css
@media (prefers-reduced-motion: no-preference) {
  .reveal {
    opacity: 0;
    transform: translateY(1.5rem);
    animation: rise 0.7s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }
  .reveal:nth-child(1) { animation-delay: 0.05s; }
  .reveal:nth-child(2) { animation-delay: 0.15s; }
  .reveal:nth-child(3) { animation-delay: 0.25s; }
  @keyframes rise {
    to { opacity: 1; transform: none; }
  }
}
```

## Scroll-triggered reveals

- CSS scroll-driven animations (`animation-timeline: view()`) for modern, JS-free reveals.
- `IntersectionObserver` when you need logic or broader support.
- Subtle parallax, pinned sections, and progress-linked motion add depth — use sparingly.

## Micro-interactions

- Hover/focus states that surprise: underline grows from a side, color sweeps, icon shifts.
- Button press feedback (scale/translate) so actions feel physical.
- Animated state transitions (loading → loaded, empty → populated) instead of hard cuts.
- Custom cursor or magnetic hover for bold directions — only if it fits the brief.

```css
.btn {
  transition: transform 0.15s ease, box-shadow 0.15s ease;
}
.btn:hover { transform: translateY(-2px); }
.btn:active { transform: translatey(0); }
```

## Accessibility — non-negotiable

Always honor reduced-motion. Gate expressive animation behind the media query and provide a
calm fallback:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

## Performance

- Animate only `transform` and `opacity` for smooth, compositor-friendly motion.
- Avoid animating `width`, `height`, `top`, `left`, or `box-shadow` in hot paths.
- Use `will-change` sparingly and remove it after the animation.
- Keep total animation work off the main thread where possible.

## Anti-patterns

- Everything fading/sliding on a timer with no hierarchy.
- Long, blocking intros the user must wait through every visit.
- Bouncy spring easing on a serious/luxury brief (tone mismatch).
- Ignoring `prefers-reduced-motion`.
