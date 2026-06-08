---
name: dieter-rams-design
description: "Use when the user mentions Dieter Rams, 'less but better', 10 principles of good design, Vitsoe, Braun design, functionalist design, minimalist design systems, honest design, unobtrusive UI, or asks for designs that prioritize usefulness over decoration, clarity over cleverness, longevity over trendiness. Also trigger when the user requests a 'Rams-style' review, wants to audit a UI against good design principles, asks for 'functional minimalism', or references any of the 10 principles by name (innovative, useful, aesthetic, understandable, unobtrusive, honest, long-lasting, thorough, environmentally friendly, as little design as possible). Use when designing or reviewing any software interface, component, or system through the lens of Dieter Rams' design philosophy."
---

# Dieter Rams: 10 Principles for Good Design

This skill applies Dieter Rams' ten principles to software interface design, component architecture, and code. It functions as both a design philosophy and a review framework — use it when creating new interfaces or auditing existing ones.

Read this file fully before writing any code.

## Core Philosophy

"Less, but better" (*Weniger, aber besser*). Design is not art — it is function made visible. Every element must earn its place by serving the user. If it doesn't help, it hurts.

Rams designed products that disappeared into daily life: honest tools that worked beautifully without demanding attention. Software should do the same. The interface is not the product — the user's goal is. The best interface is the one the user doesn't notice.

## The 10 Principles Applied to Software

### 1. Good Design Is Innovative

Innovation is not novelty. It is solving real problems in better ways. Technological progress offers new possibilities, but innovation must serve the user — not the technology itself.

**Implementation:**
- Use new capabilities (CSS Container Queries, View Transitions, Web Components) only when they solve a genuine user problem — not because they're new
- Prefer stable, well-understood patterns over bleeding-edge experiments in production
- Innovate in the problem space, not the solution space: observe users, anticipate needs, then find the simplest technology to meet them
- When building a clone or common pattern, find one meaningful improvement — even if small

**Code smell:** Using the newest framework features without a user-facing reason. Rewriting working code to use a new API when the old one still serves perfectly.

### 2. Good Design Makes a Product Useful

A product is bought to be used. It must satisfy functional, psychological, and aesthetic needs. Anything that detracts from usefulness is waste.

**Implementation:**
- Every UI element must answer: "What user need does this serve?"
- Prioritize core tasks ruthlessly. Secondary actions go behind menus, not in the primary viewport
- Measure and track the value your software delivers. If a feature isn't measurably improving user outcomes, remove it
- Satisfy psychological needs: the interface should feel trustworthy, calm, and competent — never stressful or manipulative
- Loading states, empty states, and error states are part of usefulness — design them first, not last

**Code smell:** Features added because "users might want this someday." UI elements that exist to impress rather than assist. Decorative flourishes that don't clarify.

### 3. Good Design Is Aesthetic

The aesthetic quality of a product is integral to its usefulness. Products used every day affect well-being. Only well-executed objects can be beautiful.

**Implementation:**
- Beauty in software comes from harmony: consistent spacing, aligned elements, proportional relationships
- Aesthetic code is readable, idiomatic, and well-structured. Code that pleases the eye is easier to maintain
- Use a single base spacing unit (4px or 8px). Every margin, padding, and gap must be a multiple of this unit
- Visual hierarchy through weight and position — not through decoration
- The design should look "obvious in retrospect" — the highest compliment

**Code smell:** Inconsistent spacing. Misaligned elements. Code that requires explanation to read. "Clever" one-liners that future maintainers will hate.

### 4. Good Design Makes a Product Understandable

It clarifies the product's structure. At best, it is self-explanatory — the user intuits function without instruction.

**Implementation:**
- Navigation must reveal structure. The user should always know where they are, how they got there, and how to leave
- Labels use plain language matching the user's mental model — not internal jargon
- Affordances are clear: clickable things look clickable, disabled things look disabled
- Progressive disclosure: show the essentials, reveal complexity on demand
- Error messages explain what happened, why, and what to do next — in that order
- When a design requires documentation to use, the design has failed

**Code smell:** Mystery meat navigation (icons without labels). Jargon in user-facing text. Features that require tooltips to discover. Clever abstractions that no one understands.

### 5. Good Design Is Unobtrusive

Products are tools, not decorations or works of art. Design should be neutral and restrained, leaving room for the user's self-expression.

**Implementation:**
- The interface is the frame, not the painting. It should recede during use
- Chrome (borders, backgrounds, dividers) should be minimal — prefer whitespace for separation
- Animations serve function (orientation, feedback, state change) — never decoration
- No branding in the user's workflow. Your logo in the corner is noise to someone trying to work
- Content is the hero. The interface exists to present content, not itself
- Observe users. Where they hesitate, stumble, or complain — that's where design is being noticed. Fix it

**Code smell:** Splash screens that delay access. Over-designed loading animations. Persistent branding. Modal overlays that interrupt flow. Decorative transitions.

### 6. Good Design Is Honest

It does not make a product appear more innovative, powerful, or valuable than it really is. It does not attempt to manipulate the consumer with promises that cannot be kept.

**Implementation:**
- No dark patterns: no confirm-shaming ("No thanks, I don't want to save money"), no disguised ads, no forced continuity, no sneaky pre-checked boxes
- Performance claims must be real. If it takes 3 seconds, don't show a skeleton screen that suggests it'll take 0.5
- Show real data, real counts, real availability. "Only 2 left" must mean exactly 2
- Abstractions must be honest: don't hide complexity behind a "simple" API that breaks unpredictably
- Be transparent about limitations. An honest error message builds more trust than a hidden failure
- Metrics that make you uncomfortable (test coverage, error rates, performance) should be visible — let them break the build so you fix them

**Code smell:** Fake scarcity. Hidden costs. Dark patterns. Over-promising in marketing. Error messages that blame the user. "Smart" defaults that serve the company, not the user.

### 7. Good Design Is Long-Lasting

It avoids being fashionable and therefore never appears antiquated. It lasts many years — even in a throwaway society.

**Implementation:**
- Avoid design trends. Glassmorphism, neumorphism, brutalism, and the "style of the month" will date your work
- Use timeless patterns: clear typography, logical layout, consistent spacing. These never age
- Plan for dependency evolution. Avoid coupling to APIs, frameworks, or platforms that will perish
- Bundle or vendor critical dependencies so the software can survive upstream changes
- Consider releasing source code under a liberal license so the work can be rebuilt on future platforms
- Dark mode support is not a trend — it's accessibility and longevity
- Test with real content at real scale. Lorem ipsum designs don't survive contact with reality

**Code smell:** Following Dribbble trends. Using a CSS framework's default theme without customization. Tight coupling to a single platform or API. Designs that only work with curated demo content.

### 8. Good Design Is Thorough Down to the Last Detail

Nothing must be arbitrary or left to chance. Care and accuracy in the design process show respect toward the user.

**Implementation:**
- Design every state: default, hover, focus, active, disabled, loading, empty, error, success — for every component
- Handle every error condition: network failure, timeout, permission denied, empty results, invalid input, rate limiting
- Empty states are designed states — they guide the user toward the first action, not toward a dead end
- Focus indicators must be visible and logical. Every interactive element must be keyboard-accessible
- Text must handle overflow, truncation, wrapping, and internationalization (German text is 30% longer than English)
- Think like a chess player: play against yourself. Be strict and demanding with your own work

**Code smell:** Components without loading or error states. Truncated text without a tooltip or expansion path. Missing `:focus-visible` styles. Empty states that say "No results" with no next step. Forms that lose data on error.

### 9. Good Design Is Environmentally Friendly

Design makes an important contribution to the preservation of the environment. It conserves resources and minimizes pollution throughout the product lifecycle.

**Implementation:**
- Performance is an environmental concern. Every wasted CPU cycle, every unnecessary network request, every bloated bundle consumes energy at scale
- Minimize asset size: optimize images (WebP/AVIF), tree-shake JavaScript, subset fonts to used characters
- Lazy-load content below the fold. Don't fetch data you won't display
- Dark mode reduces energy consumption on OLED displays — support it, consider making it default
- If the application isn't performing useful work, it should be inert: no polling, no background animation, no idle computation
- Choose hosting and infrastructure with renewable energy. The internet's carbon footprint is real

**Code smell:** Unoptimized images. Unused JavaScript shipped to the client. Infinite scroll without cleanup. SetInterval without clearInterval. Auto-playing video. Polling when WebSockets or SSE would suffice.

### 10. Good Design Is as Little Design as Possible

Less, but better — because it concentrates on the essential aspects, and products are not burdened with non-essentials. Back to purity, back to simplicity.

**Implementation:**
- Start by removing elements. The first question is not "what should I add?" but "what can I remove?"
- Fewer components, fewer states, fewer variations. A smaller API surface is easier to maintain, test, and understand
- Comments should be exceptional, not explanatory. If code needs a comment, rewrite the code — commented code is a design failure
- Resist the urge to over-engineer. Once the software is "barely good enough" — no defects, meets requirements, fit for purpose — it is complete
- Each dependency is a liability. Before adding a library, ask: "Can I write this in 20 lines?" If yes, write it
- The minimum viable product is not the smallest thing you can ship — it's the smallest thing that delivers value

**Code smell:** Unnecessary abstractions. "Just in case" code. Over-engineered architecture for simple problems. More than 2 typefaces. More than 4 colors. Comments that explain what readable code already says.

## The Design System

### Color
```
Maximum 4 colors total:
  --bg:         background (white or near-white; near-black for dark mode)
  --text:       primary text (high contrast against bg)
  --text-muted: secondary text (one shade only)
  --accent:     ONE functional accent for links, focus, primary actions

No gradients. No decorative color transitions.
Dark mode: swap bg/text, adjust accent saturation, nothing more.
```

### Typography
```
One typeface. System fonts preferred:
  - System UI (SF Pro, Segoe UI, Roboto)
  - Body: 16px base, 1.5 line-height
  - Hierarchy through weight (400→500→700), not excessive size jumps
  - Maximum 4 sizes: body, small, heading, large-heading
  - Line length: 45–75 characters for body text
```

### Spacing
```
Single base unit: 4px or 8px
All spacing is a multiple of this unit:
  --space-xs:  4px
  --space-sm:  8px
  --space-md:  16px
  --space-lg:  24px
  --space-xl:  32px
  --space-2xl: 48px
No ad-hoc spacing values anywhere.
```

### Component States
Every interactive component must define these states. No exceptions:

| State | Required behavior |
|-------|------------------|
| Default | Visible, accessible, correctly labeled |
| Hover | Visual feedback (cursor, color shift) |
| Focus | Visible focus ring, logical tab order |
| Active/Pressed | Confirmation of interaction |
| Disabled | Visually distinct, non-interactive, with explanation tooltip if non-obvious |
| Loading | Skeleton or spinner, prevent double-submit |
| Error | Clear message, recovery path |
| Empty | Guidance toward first action, never a dead end |

## Design Review Framework

Use this when auditing a UI against Rams principles. Output format:

```
═══════════════════════════════════════════════════
DIETER RAMS DESIGN REVIEW: [filename/component]
═══════════════════════════════════════════════════

VIOLATIONS
──────────
Principle 6 (Honest) — Line 42: Fake urgency countdown
  "Only 3 left!" is hardcoded, not real inventory
  Fix: Show real stock count or remove the claim entirely

Principle 8 (Thorough) — Line 78: Missing error state
  <form> has no error handling for network failure
  Fix: Add try/catch with user-facing error message and retry

Principle 5 (Unobtrusive) — Line 15: Autoplay video
  Hero section auto-plays video with sound
  Fix: Remove autoplay or make it muted + user-initiated

PRINCIPLES UPHELD
─────────────────
Principle 4 (Understandable) — Clear navigation structure
Principle 10 (Less is more) — Minimal markup, focused content

═══════════════════════════════════════════════════
SCORE: 7/10 principles upheld
Critical: 2   Serious: 1   Minor: 0
═══════════════════════════════════════════════════
```

**Priority levels:**
- **Critical:** Honesty violations (Principle 6), usability blockers (Principles 4, 8)
- **Serious:** Unobtrusiveness violations (Principle 5), missing states
- **Minor:** Aesthetic inconsistencies (Principle 3), improvement opportunities

## Anti-Patterns

### Never
- ❌ Dark patterns: confirm-shaming, fake scarcity, hidden costs, forced continuity, disguised ads
- ❌ Decorative elements without function (background videos, parallax, animated illustrations)
- ❌ Design trends: glassmorphism, neumorphism, brutalism, skeuomorphism (unless explicitly requested)
- ❌ More than 4 colors (background, text, muted text, accent)
- ❌ More than 2 typefaces
- ❌ Gradients (CSS `linear-gradient`, `radial-gradient`)
- ❌ Drop shadows for elevation (use borders or whitespace)
- ❌ Auto-playing content (video, audio, carousels)
- ❌ Splash screens or unnecessary modals that delay access to content
- ❌ Mystery meat navigation (unlabeled icons, hidden menus)
- ❌ Jargon in user-facing text
- ❌ Skeleton screens that misrepresent loading time
- ❌ Comments that explain what code does (refactor the code instead)

### Always
- ✅ Question every element: "What user need does this serve?"
- ✅ Design states before components — empty, loading, error, edge cases first
- ✅ Remove before adding — can you delete something to solve this?
- ✅ Use real data, real text, real edge cases in design — never lorem ipsum
- ✅ Test with keyboard, screen reader, and throttled network
- ✅ Let uncomfortable metrics be visible

## Motion & Interaction

Motion in Rams-inspired design is functional only — never decorative.

- **Duration:** 150–300ms. Never exceed 400ms.
- **Easing:** `ease-out` for entering elements, `ease-in` for exiting. No bounce, no spring, no elastic.
- **Purpose:** Motion signals state change (page transition), provides feedback (button press), or orients the user (scroll position). If the animation doesn't serve one of these purposes, remove it.
- **Reduced motion:** Always respect `prefers-reduced-motion`. Provide static alternatives for every animation.
- **Stagger:** When multiple elements enter, stagger by 30–50ms to create reading rhythm without drawing attention to the animation itself.

```css
/* Standard enter animation */
.element {
  animation: rams-enter 200ms ease-out both;
}
@keyframes rams-enter {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Stagger */
.element:nth-child(2) { animation-delay: 40ms; }
.element:nth-child(3) { animation-delay: 80ms; }

/* Respect reduced motion */
@media (prefers-reduced-motion: reduce) {
  .element { animation: none; }
}
```

## Responsive Principles

- Single-column is the default. Multi-column only when content demands it (dashboards, comparisons, data grids)
- Content determines breakpoints, not device widths. Add a breakpoint when the content breaks — nowhere else
- Mobile is not a "stripped-down" version. It is often the primary interface. Design mobile-first
- Touch targets must be ≥ 44×44px (WCAG 2.5.5)

## Checklist Before Output

1. ☐ Does every element serve a user need? (Principles 2, 5, 10)
2. ☐ Is the interface self-explanatory? (Principle 4)
3. ☐ Are all component states designed (loading, empty, error, disabled)? (Principle 8)
4. ☐ Are there any dark patterns or manipulative elements? (Principle 6)
5. ☐ Is the color palette ≤ 4 colors with no gradients? (Principles 3, 10)
6. ☐ Is typography one typeface with ≤ 4 sizes? (Principles 3, 10)
7. ☐ Are all spacing values multiples of the base unit? (Principle 8)
8. ☐ Do animations serve a functional purpose? (Principle 5)
9. ☐ Is performance intentional (optimized assets, lazy loading, no waste)? (Principle 9)
10. ☐ Would this design still look good in 10 years? (Principle 7)
11. ☐ Can I remove anything else? (Principle 10)
