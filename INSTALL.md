# Installation Guide

## Quick Install

Copy and paste this prompt into Claude Code after downloading the ZIP:

---

```
## Install Design Engineer Auditor

I'd like to install the Design Engineer Auditor agent and its design-motion-principles skill.

**Where I downloaded the ZIP**: [REPLACE WITH YOUR PATH, e.g., ~/Downloads/design-engineer-auditor.zip]

Please:
1. Ask me if I want this installed globally (available in all my projects) or just for this project
2. Extract the ZIP and copy the files to the appropriate location:
   - Global install: ~/.claude/agents/ and ~/.claude/skills/
   - Project install: ./.claude/agents/ and ./.claude/skills/
3. Verify the installation worked by checking all files exist
4. Tell me how to invoke the agent

Note: The ZIP contains:
- agents/design-engineer-auditor.md
- skills/design-motion-principles/ (folder with 10 files)
```

---

## Manual Installation

If you prefer to install manually:

### Global Installation (all projects)

```bash
# Extract the ZIP
unzip design-engineer-auditor.zip -d /tmp/dea-install

# Copy agent
cp /tmp/dea-install/agents/design-engineer-auditor.md ~/.claude/agents/

# Copy skill folder
cp -r /tmp/dea-install/skills/design-motion-principles ~/.claude/skills/

# Cleanup
rm -rf /tmp/dea-install
```

### Project Installation (this project only)

```bash
# Extract the ZIP
unzip design-engineer-auditor.zip -d /tmp/dea-install

# Create directories if needed
mkdir -p .claude/agents .claude/skills

# Copy agent
cp /tmp/dea-install/agents/design-engineer-auditor.md .claude/agents/

# Copy skill folder
cp -r /tmp/dea-install/skills/design-motion-principles .claude/skills/

# Cleanup
rm -rf /tmp/dea-install
```

## Verify Installation

After installation, verify by checking these files exist:

**Global**:
- `~/.claude/agents/design-engineer-auditor.md`
- `~/.claude/skills/design-motion-principles/SKILL.md`

**Project**:
- `./.claude/agents/design-engineer-auditor.md`
- `./.claude/skills/design-motion-principles/SKILL.md`

## Usage

Once installed, invoke the agent in Claude Code:

```
Audit the motion design in this codebase
```

Or with specific scope:

```
Audit animations in src/components/
```

## Updating

To update to a newer version, simply re-run the installation—files will be overwritten.

## Uninstalling

**Global**:
```bash
rm ~/.claude/agents/design-engineer-auditor.md
rm -rf ~/.claude/skills/design-motion-principles
```

**Project**:
```bash
rm .claude/agents/design-engineer-auditor.md
rm -rf .claude/skills/design-motion-principles
```
