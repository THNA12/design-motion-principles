# Design Engineer Auditor

A Claude Code agent + skill for motion design audits, trained on Emil Kowalski, Jakub Krehel, and Jhey Tompkins. Get per-designer feedback on your animations—restraint vs polish vs experimentation—with actionable recommendations.

## What It Does

This agent audits your codebase's motion design (CSS animations, transitions, Framer Motion, GSAP, etc.) through the lens of three distinct design philosophies:

| Designer | Philosophy | Focus |
|----------|-----------|-------|
| **Emil Kowalski** | Restraint & Purpose | "Most things don't need animation." Frequency-based decisions, <300ms durations, subtle polish |
| **Jakub Krehel** | Production Polish | Enter/exit pairs, dynamic shadows, bezier curves, optical alignment |
| **Jhey Tompkins** | Creative Experimentation | @property animations, linear() easing, 3D CSS, scroll-driven effects |

## Example Output

When you run an audit, you get per-designer feedback:

```
## Motion Design Audit: src/components/

### Emil Kowalski's Perspective
**Overall Assessment:** Good restraint, but some unnecessary flourishes

**What's Working:**
- Button hover states are subtle and fast (200ms)
- Modal transitions use appropriate easing

**Concerns:**
- Hero section parallax adds no functional value
- Loading spinner could be simpler

**Recommendations:**
- Remove parallax effect or make it opt-in
- Consider static skeleton instead of animated loader

---

### Jakub Krehel's Perspective
**Overall Assessment:** Missing production polish on key interactions

**What's Working:**
- Card hover shadows look natural

**Concerns:**
- Modal has enter animation but no exit
- Dropdown appears instantly (no transition)

**Recommendations:**
- Add exit animation to modal (reverse of enter)
- Add 150ms fade+scale to dropdown

---

### Jhey Tompkins' Perspective
**Overall Assessment:** Conservative but solid foundation

**What's Working:**
- Transitions are performant (transform/opacity only)

**Opportunities:**
- Toggle switch could use @property for smoother color transitions
- Scroll sections could benefit from scroll-driven animations

---

### Designer Reference Summary
**Primary influence:** Emil Kowalski (7 references)
**Why:** Codebase prioritizes subtle, functional animations over decorative effects.
The restraint-first philosophy aligns well with the product's professional tone.
```

## Installation

### Quick Install

1. Download `design-engineer-auditor.zip` from this repo
2. Open Claude Code in any project
3. Paste the prompt from [INSTALL.md](./INSTALL.md)
4. Choose global (all projects) or project-level installation

### Manual Install

**Global (all projects):**
```bash
unzip design-engineer-auditor.zip -d /tmp/dea
cp /tmp/dea/agents/design-engineer-auditor.md ~/.claude/agents/
cp -r /tmp/dea/skills/design-motion-principles ~/.claude/skills/
rm -rf /tmp/dea
```

**Project-level:**
```bash
unzip design-engineer-auditor.zip -d /tmp/dea
mkdir -p .claude/agents .claude/skills
cp /tmp/dea/agents/design-engineer-auditor.md .claude/agents/
cp -r /tmp/dea/skills/design-motion-principles .claude/skills/
rm -rf /tmp/dea
```

## Usage

Once installed, invoke in Claude Code:

```
Audit the motion design in this codebase
```

Or with specific scope:

```
Audit animations in src/components/
```

Or leaning toward a specific designer's philosophy:

```
Audit this codebase with a focus on Jakub's production polish perspective
```

## Requirements

- [Claude Code](https://claude.ai/code) CLI

## What's Included

```
agents/
  └── design-engineer-auditor.md    # The agent definition
skills/
  └── design-motion-principles/
      ├── SKILL.md                  # Skill entry point
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

This agent synthesizes motion design principles from:

- **Emil Kowalski** — [emilkowal.ski](https://emilkowal.ski), [animations.dev](https://animations.dev), [Sonner](https://sonner.emilkowal.ski), [Vaul](https://vaul.emilkowal.ski)
- **Jakub Krehel** — [krehel.com](https://krehel.com)
- **Jhey Tompkins** — [jhey.dev](https://jhey.dev), [@jh3yy](https://twitter.com/jh3yy)

## License

MIT
