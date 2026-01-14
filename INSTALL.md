# Installation Guide

## Quick Install

Copy and paste this prompt into Claude Code after downloading the ZIP:

---

```
## Install Design Motion Principles Skill

I'd like to install the design-motion-principles skill for motion design audits.

**Where I downloaded the ZIP**: [REPLACE WITH YOUR PATH, e.g., ~/Downloads/design-motion-principles.zip]

Please:
1. Ask me if I want this installed globally (available in all my projects) or just for this project
2. Extract the ZIP and copy the skill folder to the appropriate location:
   - Global install: ~/.claude/skills/
   - Project install: ./.claude/skills/
3. Verify the installation worked by checking all files exist
4. Tell me how to use the skill

Note: The ZIP contains:
- skills/design-motion-principles/ (folder with 10 files)
```

---

## Manual Installation

If you prefer to install manually:

### Global Installation (all projects)

```bash
# Extract the ZIP
unzip design-motion-principles.zip -d /tmp/dmp-install

# Copy skill folder
cp -r /tmp/dmp-install/skills/design-motion-principles ~/.claude/skills/

# Cleanup
rm -rf /tmp/dmp-install
```

### Project Installation (this project only)

```bash
# Extract the ZIP
unzip design-motion-principles.zip -d /tmp/dmp-install

# Create directory if needed
mkdir -p .claude/skills

# Copy skill folder
cp -r /tmp/dmp-install/skills/design-motion-principles .claude/skills/

# Cleanup
rm -rf /tmp/dmp-install
```

## Verify Installation

After installation, verify by checking these files exist:

**Global**:
- `~/.claude/skills/design-motion-principles/SKILL.md`

**Project**:
- `./.claude/skills/design-motion-principles/SKILL.md`

## Usage

Once installed, just ask Claude Code in any conversation:

```
Audit the motion design in this codebase
```

Or with specific scope:

```
Audit animations in src/components/
```

The skill will:
1. Scan your codebase to understand the project context
2. Propose a perspective weighting (Emil/Jakub/Jhey balance)
3. Wait for your confirmation
4. Provide a full audit with per-designer feedback

## Updating

To update to a newer version, simply re-run the installation—files will be overwritten.

## Uninstalling

**Global**:
```bash
rm -rf ~/.claude/skills/design-motion-principles
```

**Project**:
```bash
rm -rf .claude/skills/design-motion-principles
```
