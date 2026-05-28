# Extension Guide: Adding a New Language

> Step-by-step instructions for adding support for a new language or tech stack to polyglot-claude-kit.

---

## Overview

The polyglot-claude-kit is designed to be extensible. Adding a new language involves:

1. **Create language folder** — `language-name/`
2. **Create language-specific CLAUDE.md** — Router + skill/agent loading
3. **Create language-specific agents** — Domain experts for that language
4. **Create language-specific skills** — Patterns & best practices
5. **Create language-specific commands** — Language-specific workflows
6. **Link shared core resources** — Reference `core/` where applicable
7. **Register the language** — Update `AGENTS.md` and `LANGUAGES.md`
8. **Test thoroughly** — Validate with sample project

---

## Step 1: Create Language Folder Structure

```bash
mkdir -p language-name/{agents,skills,commands,templates,knowledge}
```

Example: Adding Node.js
```bash
mkdir -p node/{agents,skills,commands,templates,knowledge}
```

---

## Step 2: Create Language-Specific CLAUDE.md

Create `language-name/CLAUDE.md` that:

1. **Loads core agents** (code-reviewer, security-auditor, performance-analyst)
2. **Loads core skills** (architecture-patterns, testing-principles, api-design, caching, resilience, ci-cd, docker, opentelemetry)
3. **Loads language-specific agents**
4. **Loads language-specific skills**
5. **References language-specific commands**
6. **References language-specific templates**

**Template:**

```markdown
---
name: [language]-claude-kit
description: Claude expertise for [language] projects
---

# Load Core Skills (Shared)
## Architecture & Design
- ../core/skills/architecture-patterns

## API & Integration
- ../core/skills/api-design

## Testing & Quality
- ../core/skills/testing-principles

## Security
- ../core/skills/security

## Performance
- ../core/skills/caching
- ../core/skills/resilience

## Infrastructure & DevOps
- ../core/skills/ci-cd
- ../core/skills/docker
- ../core/skills/opentelemetry

---

# Load [Language]-Specific Skills

## Language Fundamentals
- ./skills/[language]-basics

## Framework/Ecosystem
- ./skills/[framework-name]

## [Add more as needed]

---

# Load Core Agents (Shared)

- ../core/agents/code-reviewer
- ../core/agents/security-auditor
- ../core/agents/performance-analyst

---

# Load [Language]-Specific Agents

- ./agents/[language]-architect
- ./agents/[specialized-agent]
- [Add more as needed]

---

# Load [Language]-Specific Commands

- /[language]-init
- /[language]-scaffold
- [Add more as needed]
```

---

## Step 3: Create Language-Specific Agents

Create agents in `language-name/agents/agent-name.md`.

**Template (based on existing agents):**

```markdown
---
name: [language]-architect
type: agent
description: |
  Expert guidance on [language] architecture, project structure, 
  module boundaries, and design decisions.
---

# [Language] Architect

## Role

You are an expert architect for [language] projects. You guide developers in:
- Architecture selection (VSA, Clean Arch, DDD, Modular Monolith)
- Project structure and folder organization
- Module boundaries and separation of concerns
- Framework selection and configuration
- Technology stack decisions

## When to Load This Agent

User signals:
- "set up project", "project structure", "architecture"
- "how should I organize", "where do I put", "folder structure"
- "which framework", "architecture decision"

## Skills This Agent Loads

1. architecture-patterns (from core)
2. [language]-basics
3. [framework-specific-skill]
4. [Add more as needed]

## Response Patterns

When asked about architecture:
1. Ask clarifying questions about project goals
2. Recommend architecture with rationale
3. Provide folder structure template
4. Link to relevant templates

[Continue with more patterns...]
```

---

## Step 4: Create Language-Specific Skills

Create skills in `language-name/skills/skill-name/SKILL.md`.

Follow the Agent Skills open standard. Each skill needs:

**SKILL.md template:**

```markdown
---
name: [skill-name]
description: >
  Brief description of what this skill covers.
  Include trigger keywords and when Claude should load it.
---

# [Skill Name]

## Core Principles

1. **Principle 1** — Explain with rationale
2. **Principle 2** — Explain with rationale
3. **Principle 3** — Explain with rationale

## Patterns

### Pattern Name
Working code example in [language], followed by explanation.

### Anti-Patterns
❌ BAD code example
✅ GOOD code example

## Decision Guide

| Scenario | Recommendation |
|----------|---|
| When [scenario 1] | Use [pattern 1] because... |
| When [scenario 2] | Use [pattern 2] because... |
```

---

## Step 5: Create Language-Specific Commands

Create commands in `language-name/commands/command-name.md`.

**Template:**

```markdown
---
name: /[language]-init
description: Interactive project initialization for [language]
---

# /[language]-init

## Purpose

Guided, step-by-step project initialization that creates:
- Project structure
- Configuration files
- Initial CLAUDE.md
- Sample code

## Workflow

1. Ask architecture questionnaire
2. Capture project metadata
3. Generate project structure
4. Create starter files
5. Initialize git
6. Output checklist

[Continue with implementation details...]
```

---

## Step 6: Create Language-Specific Templates

Create templates in `language-name/templates/template-name/`.

Each template should include:
- `CLAUDE.md` — Language-specific instructions for this template
- `README.md` — When & how to use this template
- Starter project structure
- Sample code
- Configuration files

---

## Step 7: Create Language-Specific Knowledge

Create reference docs in `language-name/knowledge/`.

Examples:
- `breaking-changes-[language].md` — Major version changes, migration guides
- `ecosystem-[language].md` — Popular packages, libraries, frameworks
- `antipatterns-[language].md` — Common mistakes specific to this language
- `architecture-decisions.md` — ADRs for this language

---

## Step 8: Create Language Stubs

Create stub folders for future languages that don't have content yet:

```bash
mkdir -p new-language
echo "# [Language Name] (Coming Soon)" > new-language/CLAUDE.md
```

---

## Step 9: Update Registry Files

### Update AGENTS.md

Add routing entries for new language agents:

```markdown
### [Language] Agents

| Agent | File | Purpose | Key Skills |
|-------|------|---------|-----------|
| **[language]-architect** | [language]/agents/[language]-architect.md | [Purpose] | [Skills] |
| [Add more] |
```

### Update LANGUAGES.md

Add entry to the status table:

```markdown
| **[Language]** | ✅ Stable / 🔜 Planned | 0.1.0 | X | Y | Z | N | [Date] |
```

And create language section with details:

```markdown
## [Language] ✅ or 🔜

**Status**: Stable / Planned  
**Folder**: `language-name/`  
**Installation**: Copy `language-name/CLAUDE.md` → `./CLAUDE.md` in your project

### What's Included
- Agents: [count]
- Skills: [count]
- Commands: [count]
- Templates: [count]

[More details...]
```

---

## Step 10: Test the New Language Kit

1. **Create a test project** in that language
2. **Copy the language CLAUDE.md** into the project root
3. **Open Claude Code**
4. **Verify agents load** — Check that the right agents are available
5. **Test a command** — Try `/[language]-init` or equivalent
6. **Test skill loading** — Ask about a pattern covered in skills
7. **Verify file references** — Ensure relative paths work
8. **Check MCP/LSP setup** — Verify language server is detected

---

## Step 11: Document Additions

Update the [LANGUAGES.md](LANGUAGES.md) roadmap and version history:

```markdown
### Phase X (Date)
✅ [Language] — [Brief description]
```

---

## Example: Adding Node.js

```bash
# 1. Create folder structure
mkdir -p node/{agents,skills,commands,templates,knowledge}

# 2. Create node/CLAUDE.md (see template above)

# 3. Create agents:
touch node/agents/node-architect.md
touch node/agents/typescript-specialist.md
touch node/agents/orm-specialist.md

# 4. Create skills:
mkdir -p node/skills/{typescript,express-fastify,async-patterns,orm-node,dependency-injection}
# ... create SKILL.md in each

# 5. Create commands:
touch node/commands/node-init.md
touch node/commands/scaffold.md

# 6. Create templates:
mkdir -p node/templates/{express-api,fastify-api,worker}

# 7. Update registry:
# - Add entries to AGENTS.md
# - Add entries to LANGUAGES.md

# 8. Test with sample Node project
```

---

## Checklist for New Language

- [ ] Folder structure created
- [ ] Language-specific `CLAUDE.md` created
- [ ] At least 1 language-specific agent created
- [ ] At least 3 language-specific skills created
- [ ] At least 2 language-specific commands created
- [ ] At least 1 template created
- [ ] Knowledge base created (antipatterns, ecosystem, breaking changes)
- [ ] AGENTS.md updated with routing
- [ ] LANGUAGES.md updated with status
- [ ] Tested with sample project
- [ ] Relative paths verified
- [ ] MCP/LSP setup documented (if applicable)

---

## Questions or Issues?

See [CONTRIBUTING.md](../CONTRIBUTING.md) for community guidelines.
