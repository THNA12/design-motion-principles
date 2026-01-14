# Design Motion Principles

A Claude Code skill for motion and interaction design audits, trained on Emil Kowalski, Jakub Krehel, and Jhey Tompkins. Get context-aware, per-designer feedback on your animations.

## What It Does

This skill audits your codebase's motion design (CSS animations, transitions, Framer Motion, GSAP, etc.) through the lens of three distinct design philosophies:

| Designer | Philosophy | Best For |
|----------|-----------|----------|
| **Emil Kowalski** | Restraint & Speed | Productivity tools, high-frequency interactions |
| **Jakub Krehel** | Production Polish | Shipped consumer apps, professional refinement |
| **Jhey Tompkins** | Creative Experimentation | Kids apps, portfolios, playful contexts |

## Key Feature: Context-Aware Weighting

The skill doesn't blindly apply rules. It first does **reconnaissance** to understand your project, then proposes a weighting:

```
## Reconnaissance Complete

**Project type**: Kids educational app, mobile-first PWA
**Existing animation style**: Spring animations (500-600ms), framer-motion
**Likely intent**: Delight and engagement for young children

**Proposed perspective weighting**:
- **Primary**: Jakub Krehel — Production polish for a shipped consumer app
- **Secondary**: Jhey Tompkins — Playful experimentation for kids
- **Selective**: Emil Kowalski — Only for high-frequency game interactions

Does this approach sound right? Should I adjust before proceeding?
```

You confirm or adjust, then get the full audit with per-designer perspectives.

## Example Output

After confirmation, you get detailed feedback from each designer:

```
### Emil's Perspective (Restraint & Speed)
[Observations specific to high-frequency interactions...]

### Jakub's Perspective (Production Polish)
[Missing exit animations, icon transitions, shadow refinements...]

### Jhey's Perspective (Experimentation & Delight)
[Opportunities for @property, scroll-driven animations, celebrations...]

### Combined Recommendations

**Critical (Must Fix)**:
| Issue | File | Action |
|-------|------|--------|
| No prefers-reduced-motion | Multiple | Add global CSS + hook |

**Important (Should Fix)**:
| Issue | File | Action |
|-------|------|--------|
| Score counter no animation | game-header.tsx | Add scale pop |
```

## Installation

### Quick Install

1. Download `design-motion-principles.zip` from this repo
2. Open Claude Code in any project
3. Paste the prompt from [INSTALL.md](./INSTALL.md)
4. Choose global (all projects) or project-level installation

### Manual Install

**Global (all projects):**
```bash
unzip design-motion-principles.zip -d /tmp/dmp
cp -r /tmp/dmp/skills/design-motion-principles ~/.claude/skills/
rm -rf /tmp/dmp
```

**Project-level:**
```bash
unzip design-motion-principles.zip -d /tmp/dmp
mkdir -p .claude/skills
cp -r /tmp/dmp/skills/design-motion-principles .claude/skills/
rm -rf /tmp/dmp
```

## Usage

Once installed, just ask Claude Code:

```
Audit the motion design in this codebase
```

Or with specific scope:

```
Audit animations in src/components/
```

The skill will automatically:
1. Do reconnaissance on your project
2. Propose a weighting based on context
3. Wait for your confirmation
4. Provide the full per-designer audit

## Requirements

- [Claude Code](https://claude.ai/code) CLI

## What's Included

```
skills/
  └── design-motion-principles/
      ├── SKILL.md                  # Main skill with workflow
      ├── emil-kowalski.md          # Emil's philosophy & techniques
      ├── jakub-krehel.md           # Jakub's philosophy & techniques
      ├── jhey-tompkins.md          # Jhey's philosophy & techniques
      ├── philosophy.md             # Synthesized design philosophy
      ├── technical-principles.md   # Implementation patterns
      ├── accessibility.md          # Motion accessibility guidelines
      ├── performance.md            # Performance best practices
      ├── audit-checklist.md        # Structured audit criteria
      └── common-mistakes.md        # Anti-patterns to flag
```

## Credits

This skill synthesizes motion design principles from:

- **Emil Kowalski** — [emilkowal.ski](https://emilkowal.ski), [animations.dev](https://animations.dev), [Sonner](https://sonner.emilkowal.ski), [Vaul](https://vaul.emilkowal.ski)
- **Jakub Krehel** — [krehel.com](https://krehel.com)
- **Jhey Tompkins** — [jhey.dev](https://jhey.dev), [@jh3yy](https://twitter.com/jh3yy)

## License

MIT
