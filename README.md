<p align="center">
  <h1 align="center">polyglot-claude-kit</h1>
  <p align="center">
    <strong>Make Claude Code an expert across your entire tech stack.</strong>
    <br />
    One extensible kit for .NET, Node.js, Go, React, Angular, and beyond.
    <br />
    <strong>v0.1.0</strong> — .NET 10 / C# 14 Stable • Multi-Language Ready
  </p>
</p>

---

## What This Is

**polyglot-claude-kit** is a curated, multi-language toolkit for Claude Code that makes AI dramatically better at understanding and generating code across different tech stacks.

Start with **.NET expertise** (10 specialist agents, 42 skills, 16 commands), then extend to **Node.js, Go, React, Angular** as you need them — all from a single repository.

---

## The Problem

Claude Code is powerful, but it's generic. When you work with .NET, it doesn't know:
- Your architecture preferences (VSA vs. Clean vs. DDD)
- Modern patterns (primary constructors, records, TimeProvider)
- Your framework choices (Minimal APIs, EF Core, xUnit)
- Your project conventions

**polyglot-claude-kit fixes this** with language-specific expertise that activates immediately when Claude Code detects your project type.

---

## Quick Start

### For .NET Projects

```bash
# 1. Copy the .NET kit into your project
cp polyglot-claude-kit/dotnet/CLAUDE.md ./CLAUDE.md

# 2. Open Claude Code in VS Code
# 3. Try a command:
/dotnet-init        # Interactive project setup
/plan               # Architecture planning
/scaffold           # Feature generation
/code-review        # Multi-dimensional review
```

### For Node.js Projects (Coming Soon)

```bash
cp polyglot-claude-kit/node/CLAUDE.md ./CLAUDE.md
```

### For Go Projects (Coming Soon)

```bash
cp polyglot-claude-kit/go/CLAUDE.md ./CLAUDE.md
```

---

## What's Included

### .NET 10 / C# 14 ✅ (Stable)

| Category | Count | Examples |
|----------|-------|----------|
| **Agents** | 10 | dotnet-architect, api-designer, ef-core-specialist, test-engineer, security-auditor, performance-analyst, devops-engineer, code-reviewer, build-error-resolver, refactor-cleaner |
| **Skills** | 42 | modern-csharp, architecture-patterns, minimal-api, ef-core, testing, serilog, aspire, docker, ci-cd, and more |
| **Commands** | 16 | /dotnet-init, /scaffold, /plan, /verify, /code-review, /security-scan, /health-check, /migrate, /tdd, /build-fix, /wrap-up, and more |
| **Templates** | 3 | web-api, modular-monolith, worker-service |
| **MCP Tools** | Roslyn Navigator | Token-efficient semantic code analysis |
| **Knowledge** | 10+ docs | Architecture patterns, API design, testing, breaking changes, antipatterns, package recommendations |

**Get started**: See [dotnet/CLAUDE.md](dotnet/CLAUDE.md)

### Node.js / TypeScript 🔜 (Planned)

**ETA**: TBD

Planned features:
- Async/await patterns & best practices
- Express.js, Fastify frameworks
- TypeScript configuration
- Jest + testing-library
- ORM: TypeORM, Prisma, Sequelize
- Dependency injection & module patterns

### Go 🔜 (Planned)

**ETA**: TBD

Planned features:
- Goroutines & concurrency
- Standard library HTTP
- Popular frameworks: Gin, Echo, Fiber
- Go testing patterns
- ORM: gorm, sqlc

### React 🔜 (Planned)

**ETA**: TBD

Planned features:
- React hooks & components
- TypeScript in React
- State management patterns
- Testing: Jest, React Testing Library

### Angular 🔜 (Planned)

**ETA**: TBD

Planned features:
- Components, directives, services
- RxJS & Observables
- Dependency injection
- Angular testing patterns

---

## Architecture

The kit is organized for **maximum reusability** and **easy extension**:

```
polyglot-claude-kit/
├── core/                          # Shared across all languages
│   ├── agents/                    # code-reviewer, security-auditor, performance-analyst
│   ├── skills/                    # architecture, api-design, testing, caching, resilience, ci-cd, docker, opentelemetry
│   ├── commands/                  # /plan, /verify, /code-review, /security-scan, /health-check
│   ├── docs/                      # Architecture patterns, API design, testing, deployment
│   └── knowledge/                 # Antipatterns, security checklist, performance tuning
│
├── dotnet/                        # .NET / C# language-specific
│   ├── CLAUDE.md                  # Copy this into .NET projects
│   ├── agents/                    # 10 specialist agents
│   ├── skills/                    # 42 comprehensive skills
│   ├── commands/                  # 16 slash commands
│   ├── templates/                 # 3 starter templates
│   ├── knowledge/                 # Breaking changes, antipatterns, packages, ADRs
│   ├── mcp/                       # Roslyn Navigator
│   └── hooks/                     # Git hooks for quality
│
├── node/                          # Node.js / TypeScript (stub)
├── go/                            # Go (stub)
├── frontend/
│   ├── react/                     # React (stub)
│   └── angular/                   # Angular (stub)
│
├── CLAUDE.md                      # Router (points to language-specific files)
├── AGENTS.md                      # Agent registry & routing
├── LANGUAGES.md                   # Status of all supported languages
├── EXTENSION-GUIDE.md             # How to add new languages
├── README.md                      # This file
└── LICENSE
```

---

## Key Features

### 🎯 Agent-Driven

Claude Code detects your project type and **automatically loads the right specialist agents**:

- `.csproj` files? → Load .NET agents
- `package.json` + TypeScript? → Load Node agents (when ready)
- `go.mod`? → Load Go agents (when ready)

### 🧠 Skill-Based

Each agent loads **relevant skills** (patterns, best practices, decision guides) on-demand:

- Architects load architecture patterns, project structure, scaffolding
- API designers load minimal APIs, versioning, OpenAPI patterns
- Test engineers load testing strategies, coverage patterns

### 🚀 Slash Commands

16 commands cover the full development lifecycle:

```
/plan              Architecture planning
/scaffold          Feature generation
/verify            7-phase verification
/code-review       Multi-dimensional review
/security-scan     OWASP + secrets audit
/health-check      Project assessment
/build-fix         Error fixing
/migrate           EF Core migrations
```

### 🔧 MCP Tools

Roslyn Navigator (for .NET) provides **10x token-efficient code analysis** via semantic queries instead of file scanning.

### 📚 Knowledge Base

Common antipatterns, breaking changes, package recommendations, architecture decision records — all searchable and contextual.

---

## When to Use Each Language Kit

| Tech Stack | Use This | When |
|-----------|----------|------|
| .NET 10, C# 14, ASP.NET Core | `dotnet/CLAUDE.md` | ✅ Now |
| REST APIs, Microservices | `dotnet/CLAUDE.md` | ✅ Now |
| EF Core, LINQ queries | `dotnet/CLAUDE.md` | ✅ Now |
| Node.js, Express, TypeScript | `node/CLAUDE.md` | 🔜 Coming |
| Go HTTP services, gRPC | `go/CLAUDE.md` | 🔜 Coming |
| React SPAs, hooks | `frontend/react/CLAUDE.md` | 🔜 Coming |
| Angular apps, RxJS | `frontend/angular/CLAUDE.md` | 🔜 Coming |

---

## Contributing: Add a New Language

Want to add support for a new language or tech stack? It's designed for this:

1. Create folder: `language-name/`
2. Create language-specific agents, skills, commands
3. Reference shared core where applicable
4. Update registry files: `AGENTS.md`, `LANGUAGES.md`
5. Done! ✅

See [EXTENSION-GUIDE.md](EXTENSION-GUIDE.md) for detailed steps.

---

## Philosophy

✅ **Guided over prescriptive** — We ask the right questions, then recommend  
✅ **Shared core, specialized leaves** — Generic patterns in `core/`, language-specific in language folders  
✅ **Token-conscious** — Every skill respects context window limits  
✅ **Practical over theoretical** — Every recommendation includes code + "why"  
✅ **Extensible from day one** — New languages add their own folders without breaking existing workflows  

---

## Resources

- **Get Started**: [dotnet/CLAUDE.md](dotnet/CLAUDE.md) for .NET projects
- **All Languages**: [LANGUAGES.md](LANGUAGES.md) — Status & roadmap
- **Agent Registry**: [AGENTS.md](AGENTS.md) — How agents route & load skills
- **Add New Language**: [EXTENSION-GUIDE.md](EXTENSION-GUIDE.md)
- **Contributing**: [CONTRIBUTING.md](CONTRIBUTING.md)

---

## Version & Changelog

**Current**: v0.1.0 (May 28, 2026)

- ✅ .NET 10 / C# 14 support (10 agents, 42 skills, 16 commands)
- ✅ Extensible architecture for multi-language support
- ✅ Core shared skills, agents, commands
- 🔜 Node.js / TypeScript (planned)
- 🔜 Go (planned)
- 🔜 React (planned)
- 🔜 Angular (planned)

---

## License

See [LICENSE](LICENSE) for details.

---

**Ready to get started?**

👉 **[For .NET Projects: Copy dotnet/CLAUDE.md](dotnet/CLAUDE.md)**

👉 **[All Languages & Status: See LANGUAGES.md](LANGUAGES.md)**

👉 **[Want to Add a Language? See EXTENSION-GUIDE.md](EXTENSION-GUIDE.md)**
