# polyglot-claude-kit — Language Router

> This is an extensible, multi-language Claude Code toolkit. Start with .NET, extend to Node.js, Go, React, Angular as needed.

## How to Use This Kit

This toolkit is organized by **language**. Copy the appropriate `CLAUDE.md` into your project root:

### For .NET / C# Projects
```bash
cp dotnet/CLAUDE.md ./CLAUDE.md
```

### For Node.js / TypeScript Projects (Coming Soon)
```bash
cp node/CLAUDE.md ./CLAUDE.md
```

### For Go Projects (Coming Soon)
```bash
cp go/CLAUDE.md ./CLAUDE.md
```

### For React Projects (Coming Soon)
```bash
cp frontend/react/CLAUDE.md ./CLAUDE.md
```

### For Angular Projects (Coming Soon)
```bash
cp frontend/angular/CLAUDE.md ./CLAUDE.md
```

---

## Repository Structure

```
polyglot-claude-kit/
├── core/                          # Shared across all languages
│   ├── agents/                    # Generic code-reviewer, security-auditor, performance-analyst
│   ├── skills/                    # Architecture, caching, resilience, CI/CD, Docker, OpenTelemetry
│   ├── commands/                  # Generic /plan, /verify, /code-review, /security-scan, etc.
│   ├── docs/                      # Architecture patterns, API design, testing, deployment guides
│   └── knowledge/                 # Antipatterns, security checklist, performance tuning
│
├── dotnet/                        # .NET / C# language-specific
│   ├── CLAUDE.md                  # Copy this into .NET projects
│   ├── agents/                    # dotnet-architect, api-designer, ef-core-specialist, etc.
│   ├── skills/                    # modern-csharp, minimal-api, ef-core, serilog, aspire, etc.
│   ├── commands/                  # /dotnet-init, /scaffold, /build-fix, /migrate, etc.
│   ├── templates/                 # web-api, modular-monolith, worker-service
│   ├── knowledge/                 # breaking-changes, antipatterns, packages, ADRs
│   ├── mcp/                       # Roslyn Navigator (code intelligence)
│   └── hooks/                     # Git hooks for quality enforcement
│
├── node/                          # Node.js / TypeScript (stub, coming soon)
│   └── CLAUDE.md
│
├── go/                            # Go language (stub, coming soon)
│   └── CLAUDE.md
│
├── frontend/
│   ├── react/                     # React (stub, coming soon)
│   │   └── CLAUDE.md
│   └── angular/                   # Angular (stub, coming soon)
│       └── CLAUDE.md
│
├── README.md                      # This file
├── AGENTS.md                      # Agent routing across all languages
├── LANGUAGES.md                   # Registry of supported languages
├── EXTENSION-GUIDE.md             # How to add new languages
├── LICENSE
└── CONTRIBUTING.md
```

---

## Quick Start

1. **Identify your project type** — Is it .NET, Node.js, Go, React, or Angular?

2. **Copy the language-specific CLAUDE.md** into your project root:
   ```bash
   cp polyglot-claude-kit/dotnet/CLAUDE.md ./CLAUDE.md
   ```

3. **Open Claude Code in your project** and start using slash commands:
   ```
   /plan                    # Architecture planning
   /scaffold                # Feature generation
   /code-review             # Multi-dimensional code review
   /verify                  # 7-phase verification
   ```

4. **For MCP tools** (if using .NET), install Roslyn Navigator:
   ```bash
   dotnet tool install -g CWM.RoslynNavigator
   ```

---

## Agent Routing

See [AGENTS.md](AGENTS.md) for the complete agent registry and routing logic.

**Core agents** (available in all languages):
- `code-reviewer` — Multi-dimensional code review
- `security-auditor` — Security vulnerability audit
- `performance-analyst` — Performance and optimization guidance

**Language-specific agents** — See your language's CLAUDE.md file.

---

## Supported Languages

| Language | Status | Details |
|----------|--------|---------|
| **.NET 10 / C# 14** | ✅ Stable | 10 agents, 42 skills, 16 commands, templates, MCP tools |
| **Node.js / TypeScript** | 🔜 Coming Soon | Planned |
| **Go** | 🔜 Coming Soon | Planned |
| **React** | 🔜 Coming Soon | Planned |
| **Angular** | 🔜 Coming Soon | Planned |

See [LANGUAGES.md](LANGUAGES.md) for detailed status and roadmap.

---

## For Contributors: Adding a New Language

If you want to add support for a new language or tech stack, see [EXTENSION-GUIDE.md](EXTENSION-GUIDE.md).

---

## Philosophy

✅ **Guided over prescriptive** — We ask the right questions, then recommend with rationale  
✅ **Shared core, specialized leaves** — Generic patterns in `core/`, language-specific expertise in language folders  
✅ **Token-conscious** — Every skill respects context window limits  
✅ **Practical over theoretical** — Every recommendation includes code examples and "why"  
✅ **Extensible from day one** — New languages add their own folders without breaking existing workflows  

---

## License

See [LICENSE](LICENSE) for terms.
