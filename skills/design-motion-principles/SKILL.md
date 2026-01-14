---
description: Expert motion and interaction design auditor based on Emil Kowalski, Jakub Krehel, and Jhey Tompkins' techniques. Use when reviewing UI animations, transitions, hover states, or any motion design work.
---

# Design Motion Audit Skill

This skill provides expert-level motion and interaction design auditing based on the combined wisdom of three design engineers:
- **Emil Kowalski** (Linear, ex-Vercel) — Restraint, speed, purposeful motion
- **Jakub Krehel** (jakub.kr) — Subtle production polish, professional refinement
- **Jhey Tompkins** (@jh3yy) — Playful experimentation, CSS innovation

## When to Use This Skill

- Reviewing animations and transitions in UI code
- Auditing motion design for production readiness
- Evaluating enter/exit animations, hover states, and state transitions
- Checking accessibility (prefers-reduced-motion)
- Assessing performance impact of animations
- Providing feedback on easing, timing, and visual effects

## Audit Workflow

### 1. Philosophy Check (Do First)
Before reviewing any technical details, ask:
- **How often will users trigger this?** (High frequency = less/no animation)
- Does this animation serve a purpose? (orientation, feedback, continuity)
- Will users notice this consciously? (If yes for production UI, probably too much)
- Does this feel natural after the 10th interaction?
- Is the easing appropriate for the brand/context?
- Is the duration appropriate? (Emil: under 300ms for productivity tools; others may vary)

### 2. Technical Review
Use the supporting files for detailed guidance:

**Designer Reference Files** (use for per-designer perspective):
- `emil-kowalski.md` — Restraint philosophy, frequency rules, clip-path, Sonner/Vaul patterns
- `jakub-krehel.md` — Production polish, enter/exit recipes, shadows, optical alignment
- `jhey-tompkins.md` — Playful experimentation, @property, linear(), 3D CSS, scroll-driven

**Topical Reference Files**:
- `philosophy.md` — Comparison of all three mindsets, when to apply each
- `technical-principles.md` — Comprehensive technical reference (all techniques)
- `accessibility.md` — prefers-reduced-motion, motion sensitivity
- `performance.md` — will-change, GPU layers, animation budget
- `common-mistakes.md` — What to avoid from all three perspectives
- `audit-checklist.md` — Structured review checklist

### 3. Feedback Structure
When providing feedback, use **per-designer perspectives**:
1. **Overall Assessment**: Does this feel polished? Too much? Too little?
2. **Emil's Perspective**: Should these animate? Frequency/speed issues?
3. **Jakub's Perspective**: Are animations polished? Enter/exit/shadows/alignment?
4. **Jhey's Perspective**: Creative opportunities? Advanced techniques?
5. **Combined Recommendations**: Prioritized actions synthesizing all three
6. **Designer Reference Summary**: Who was referenced most and why? How to lean differently?

## Quick Reference: Core Principles

### Enter Animation Recipe
```jsx
initial={{ opacity: 0, translateY: 8, filter: "blur(4px)" }}
animate={{ opacity: 1, translateY: 0, filter: "blur(0px)" }}
transition={{ type: "spring", duration: 0.45, bounce: 0 }}
```

### Exit Animation Subtlety
Exits should be subtler than enters. Use fixed small values instead of full movement.

### Easing Selection
| Easing | Use For |
|--------|---------|
| `ease-out` | Elements entering view |
| `ease-in` | Elements leaving view |
| `spring (bounce: 0)` | Professional interactive elements |
| `spring (bounce > 0)` | Playful/fun contexts only |

### The Golden Rule
> "The best animation is that which goes unnoticed."

If users comment "nice animation!" on every interaction, it's probably too prominent.

## Supporting Files

### Designer References (for per-designer perspectives)
- [Emil Kowalski](emil-kowalski.md) — Restraint, frequency rules, speed, Sonner/Vaul patterns
- [Jakub Krehel](jakub-krehel.md) — Production polish, enter/exit, shadows, optical alignment
- [Jhey Tompkins](jhey-tompkins.md) — Playful experimentation, @property, linear(), 3D CSS

### Topical References
- [Philosophy](philosophy.md) — Comparing all three mindsets, when to apply each
- [Technical Principles](technical-principles.md) — Comprehensive technical reference
- [Accessibility](accessibility.md) — Motion sensitivity and reduced-motion support
- [Performance](performance.md) — GPU acceleration and optimization
- [Common Mistakes](common-mistakes.md) — What to avoid
- [Audit Checklist](audit-checklist.md) — Systematic review checklist
