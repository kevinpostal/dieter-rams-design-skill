# dieter-rams-design-skill

[![MIT License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
[![OpenCode](https://img.shields.io/badge/made%20for-opencode-6e56cf)](https://github.com/anomalyco/opencode)
[![Claude Code](https://img.shields.io/badge/works%20with-Claude%20Code-d97706)](https://claude.ai)
[![10 Principles](https://img.shields.io/badge/principles-10-2563eb)](https://www.vitsoe.com/gb/about/good-design)

> An AI skill that turns Dieter Rams' 10 principles of good design into actionable rules for software. Build interfaces that are useful, honest, unobtrusive, and built to last — or audit existing ones against the standard that defined Braun and Vitsoe.
>
> *"Less, but better"* — Dieter Rams

## Examples

Seven use cases. Each follows the skill's principles: ≤4 colors, no shadows, no gradients, system typography, all states designed.

| Use case | What it demonstrates |
|----------|---------------------|
| [Dashboard](#dashboard) | Asymmetric layout, functional metrics, thorough activity feed |
| [Editorial](#editorial) | Content-first reading, restrained chrome, single accent |
| [Settings form](#settings) | All component states — default, focus, error, disabled, success |
| [Product page](#product) | Honest pricing, real inventory, no dark patterns |
| [Mobile tasks](#mobile-tasks) | Mobile-first, sticky header, completion states |
| [Data table](#data-table) | Sortable columns, status badges, pagination |
| [Design review](#design-review) | The review framework applied to real components |

### Dashboard

Project management dashboard in light and dark modes. Four metric cards, active project list with progress bars, recent activity feed. One typeface, one accent color, zero decoration.

![Dashboard](dashboard_light.png) ![Dashboard dark](dashboard_dark.png)

### Editorial

Long-form article with pull quotes, blockquotes, and footnotes. Single-column content, 680px max-width, 45–75 characters per line. The interface recedes.

![Editorial](editorial_light.png) ![Editorial dark](editorial_dark.png)

### Settings

Account settings form showing every component state: empty field, filled field, focused field (blue ring), error with helpful message, disabled input, verification success, and a danger zone with destructive action. Thorough down to the last detail.

![Settings form](settings.png)

### Product

E-commerce product page built on honest design. Real stock count — not fake urgency. Transparent shipping costs. No pre-checked upsells. Variants show real availability (struck through when out of stock). Free returns stated upfront.

![Product page](product.png)

### Mobile tasks

Daily task planner at 390px width. Sticky header, horizontal date strip with selected day, sectioned task list with completion states, tag system for context, bottom tab bar. Mobile isn't a stripped-down desktop.

![Mobile tasks](mobile.png)

### Data table

Deployments table with sortable columns, status badges (active, warning, error, superseded), user avatars, summary statistics, and pagination. Every row is scannable; every state is designed.

![Data table](table.png)

### Design review

The skill's review framework in action — auditing a checkout component. Each finding cites the principle violated, the location, the violation, and a concrete fix. Violations prioritized: honesty = critical, thoroughness = serious, aesthetics = minor.

![Design review](review.png)

## The 10 principles

| # | Principle | Software application |
|---|-----------|----------------------|
| 1 | **Innovative** | New tech only when it solves a real user problem — not for its own sake |
| 2 | **Useful** | Every UI element serves a need; remove anything that doesn't |
| 3 | **Aesthetic** | Beauty from harmony, proportion, and consistency — not decoration |
| 4 | **Understandable** | Self-explanatory interfaces; no documentation required to use |
| 5 | **Unobtrusive** | The interface is a tool; it recedes during use |
| 6 | **Honest** | No dark patterns; show real data, real counts, real limitations |
| 7 | **Long-lasting** | Avoid trends; use timeless patterns that age well |
| 8 | **Thorough** | Design every state — loading, empty, error, disabled, success |
| 9 | **Environmentally friendly** | Performance is ethics; minimize resource consumption |
| 10 | **As little as possible** | Less, but better — delete before adding |

Full implementation guidance in [SKILL.md](SKILL.md).

## Installation

```bash
# opencode
cp -r dieter-rams-design-skill ~/.config/opencode/skills/

# Claude Code
cp -r dieter-rams-design-skill ~/.claude/skills/
```

The skill activates automatically. The `SKILL.md` file is the only required file.

## Trigger phrases

The skill loads when the AI assistant detects any of:

- "Dieter Rams", "less but better", "10 principles of good design"
- "Vitsoe", "Braun design", "functionalist design"
- "Honest design", "unobtrusive UI", "functional minimalism"
- "Rams-style review", "Rams-inspired"
- Any of the 10 principles by name
- Requests to audit a UI against good design principles

## Design review framework

```
═══════════════════════════════════════════════════
DIETER RAMS DESIGN REVIEW: CheckoutFlow.tsx
═══════════════════════════════════════════════════

VIOLATIONS
──────────
Principle 6 (Honest) — Line 42: Fake urgency countdown
  "Only 3 left!" is hardcoded, not real inventory
  Fix: Show real stock count or remove the claim entirely

PRINCIPLES UPHELD
─────────────────
Principle 2 (Useful) — Clear, focused checkout flow
Principle 4 (Understandable) — Step labels match user mental model

═══════════════════════════════════════════════════
SCORE: 7/10 principles upheld
Critical: 1   Serious: 2   Minor: 0
═══════════════════════════════════════════════════
```

Priority levels:
- **Critical** — Honesty violations, usability blockers
- **Serious** — Unobtrusiveness violations, missing states
- **Minor** — Aesthetic inconsistencies, improvement opportunities

## Design system

```
Color   4 max: bg, text, text-muted, accent
Type    1 family (system), 4 sizes max, weight for hierarchy
Space   4px or 8px base unit, all values are multiples
States  Default · Hover · Focus · Active · Disabled · Loading · Error · Empty
Motion  Functional only, 150–300ms, ease-out, no bounce
```

## Resources

- [Dieter Rams: 10 Principles for Good Design (Vitsoe)](https://www.vitsoe.com/gb/about/good-design)
- [Dieter Rams' 10 Principles Applied to Software](https://github.com/zedr/dieter-rams-10-applied-to-software) by zedr
- [tenprinciples.design](https://tenprinciples.design) by joe-bell
- [A Practical Guide to Design Principles (Smashing Magazine)](https://www.smashingmagazine.com/2026/04/practical-guide-design-principles/)
- [Rams Design Review](https://gist.github.com/keskinonur/ae1a3f4ae83d3f5df43b84d6f28dd1ca) by keskinonur

## Related

- [bauhaus-design-skill](https://github.com/capsrock/bauhaus-design-skill) — Visual principles: grids, typography, geometric abstraction. Use with this skill for visual structure.
- [principles (elementary OS)](https://github.com/cassidyjames/principles) — A reminder app for the 10 principles

## Inspired by

Dieter Rams, whose work at Braun (1955–1995) and Vitsoe defined what good design means.

## License

MIT
