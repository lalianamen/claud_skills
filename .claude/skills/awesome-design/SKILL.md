---
name: awesome-design
description: One command for three "awesome design" libraries kept in awesome-design/ — 84 DESIGN.md breakdowns of real brands (Stripe, Linear, Apple…), 67 named style skills (minimal, editorial, neon, retro…), and Claude Design style families, remix recipes and prompts. Use when the owner wants a page to look like a known brand or a named style, wants to pick a visual direction, or asks what designs are available.
---

# Awesome Design

The libraries live in `awesome-design/` at the root of the claud_skills repo
(from this file: `../../../awesome-design/`). They are reference files, not
installed skills: read only the one or two files the request needs.

| Folder | What is inside | Use when the owner says |
|---|---|---|
| `voltagent-design-md/design-md/<brand>/DESIGN.md` | 84 brand design systems: colors, type, spacing, components, do/don't | "like Stripe", "в стиле Apple" |
| `bergside-design-skills/skills/<style>/SKILL.md` (+ `DESIGN.md`) | 67 named styles; `skills/index.json` lists them | "minimal", "brutalism", "neon", "retro", "paper" |
| `rohitg00-claude-design/design-md/<family>/<brand>.md` | 9 aesthetic families: editorial, terminal, warm, data-dense, cinematic, playful, glass, brutalist, indie; `remix/` mixes two brands | "тёплый", "кинематографичный", "смешай Linear и Claude" |
| `rohitg00-claude-design/prompts/`, `recipes/` | Ready prompts (family picker, audit a live site, break the default look) and step-by-step recipes (landing page in 20 min, brand extraction) | "помоги выбрать стиль", "сделай лендинг по рецепту" |

## Steps

1. Match the request to a folder above. `ls` the folder to find the exact name;
   brand folders use the domain name for some (`linear.app`, `mistral.ai`).
2. Nothing named? Ask the owner one question: a brand they like, or a mood.
   Or run `rohitg00-claude-design/prompts/family-picker.md` (3 questions).
   For "what is there?" list the folder names instead of reading files.
3. Read the chosen file and turn it into tokens for the project: colors, fonts,
   spacing, radius, component rules. Say which file you used.
4. Build or restyle with those tokens. These files describe other companies'
   brands: take the system (scale, rhythm, rules), not their logo, name, or
   exact copy. When `/frontend-design` is available, follow it too; a named
   reference wins over its "avoid defaults" list.
5. Keep the project's own rules (for LICENA: brand tokens, EN/ES/RU, render check).
