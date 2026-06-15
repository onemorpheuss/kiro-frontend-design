# Frontend Design

A Kiro Power that generates distinctive, production-grade frontend interfaces and avoids
generic "AI slop" aesthetics. Adapted for Kiro from Anthropic's `frontend-design` skill.

## What it does

Kiro automatically reaches for this power on frontend work. It produces production-ready
code with:

- Bold, intentional aesthetic direction
- Distinctive typography and cohesive color systems
- High-impact animations and meticulous visual detail
- Context-aware, accessible, responsive implementation

## Usage

Just describe what you want to build:

```
"Create a dashboard for a music streaming app"
"Build a landing page for an AI security startup"
"Design a settings panel with dark mode"
```

Kiro chooses a clear aesthetic direction and implements production code with attention to
detail.

## Structure

```
frontend-design/
├── POWER.md                          # Power manifest + overview
├── README.md
└── steering/
    ├── 01-design-thinking.md         # Pick the aesthetic direction first
    ├── 02-aesthetics-guidelines.md   # Core aesthetics reference
    ├── 03-typography-and-color.md    # Fonts + color systems
    ├── 04-motion-and-animation.md    # Motion + page-load orchestration
    ├── 05-implementation.md          # HTML/React/Vue/Tailwind, responsive, a11y
    └── 06-avoiding-ai-slop.md        # Audit + fix generic AI tells
```

## Install

Place this folder under your Kiro powers directory and open the Powers panel in the IDE:

- User level: `~/.kiro/powers/installed/frontend-design/`
- Or publish the folder to a git repo and install it via the Powers panel.

## Credit

Adapted from the [Anthropic Frontend Design plugin](https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design)
and the [Frontend Aesthetics Cookbook](https://github.com/anthropics/claude-cookbooks/blob/main/coding/prompting_for_frontend_aesthetics.ipynb).
Content was rephrased and restructured for Kiro's Power/steering format.
