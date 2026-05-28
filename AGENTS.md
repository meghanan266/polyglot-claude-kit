# Agent Registry & Routing

> This file defines how Claude Code routes queries to specialist agents across all languages.

---

## Core Agents (Multi-Language)

These agents are available in **all** language contexts. Load them whenever the context calls for:

| Agent | File | Purpose | When to Use |
|-------|------|---------|------------|
| **code-reviewer** | [core/agents/code-reviewer.md](core/agents/code-reviewer.md) | Multi-dimensional code review | "review this code", "PR review", "code quality" |
| **security-auditor** | [core/agents/security-auditor.md](core/agents/security-auditor.md) | Security vulnerability audit | "security", "authentication", "OWASP", "authorize" |
| **performance-analyst** | [core/agents/performance-analyst.md](core/agents/performance-analyst.md) | Performance profiling & optimization | "performance", "benchmark", "memory", "caching" |

---

## Language-Specific Agents

### .NET / C# Agents

| Agent | File | Purpose | Key Skills |
|-------|------|---------|-----------|
| **dotnet-architect** | [dotnet/agents/dotnet-architect.md](dotnet/agents/dotnet-architect.md) | Architecture decisions, project structure, scaffolding | architecture-advisor, project-structure, vertical-slice, clean-architecture, ddd |
| **api-designer** | [dotnet/agents/api-designer.md](dotnet/agents/api-designer.md) | Minimal APIs, OpenAPI, versioning | minimal-api, api-versioning, authentication, error-handling |
| **ef-core-specialist** | [dotnet/agents/ef-core-specialist.md](dotnet/agents/ef-core-specialist.md) | Database, queries, migrations | ef-core, configuration, migration-workflow |
| **test-engineer** | [dotnet/agents/test-engineer.md](dotnet/agents/test-engineer.md) | Test strategy, coverage | testing |
| **build-error-resolver** | [dotnet/agents/build-error-resolver.md](dotnet/agents/build-error-resolver.md) | Autonomous build error fixing | autonomous-loops, ef-core, dependency-injection |
| **refactor-cleaner** | [dotnet/agents/refactor-cleaner.md](dotnet/agents/refactor-cleaner.md) | Dead code removal, cleanup | de-sloppify, testing, ef-core |

### Node.js / TypeScript Agents (Coming Soon)

| Agent | File | Purpose |
|-------|------|---------|
| (stub) | node/agents/ | (Planned) |

### Go Agents (Coming Soon)

| Agent | File | Purpose |
|-------|------|---------|
| (stub) | go/agents/ | (Planned) |

### React Agents (Coming Soon)

| Agent | File | Purpose |
|-------|------|---------|
| (stub) | frontend/react/agents/ | (Planned) |

### Angular Agents (Coming Soon)

| Agent | File | Purpose |
|-------|------|---------|
| (stub) | frontend/angular/agents/ | (Planned) |

---

## Routing Logic

### Step 1: Detect Project Type

Claude Code detects project context:
- **`.csproj` files** → Load .NET agents + core agents
- **`package.json` + `tsconfig.json`** → Load Node agents + core agents (when available)
- **`go.mod` file** → Load Go agents + core agents (when available)
- **`angular.json` + `package.json`** → Load Angular agents + core agents (when available)
- **`react` in `package.json` + `tsconfig.json`** → Load React agents + core agents (when available)

### Step 2: Load Agent Skills

Each agent loads its dependencies:

**dotnet-architect** loads:
- modern-csharp (baseline)
- architecture-advisor
- project-structure
- scaffolding
- vertical-slice
- clean-architecture
- ddd

**api-designer** loads:
- modern-csharp
- minimal-api
- api-versioning
- authentication
- error-handling

**ef-core-specialist** loads:
- modern-csharp
- ef-core
- configuration
- migration-workflow

**test-engineer** loads:
- modern-csharp
- testing

**code-reviewer** loads (all languages):
- code-review-workflow
- convention-learner
- contextual skills based on files under review

**security-auditor** loads (all languages):
- authentication
- configuration

**performance-analyst** loads (all languages):
- caching

---

## Routing Table: User Intent → Agent

| User Intent Pattern | Primary Agent | Support Agent | Context |
|---|---|---|---|
| "set up project", "folder structure", "architecture" | dotnet-architect | — | .NET only |
| "create endpoint", "API route", "OpenAPI", "swagger" | api-designer | — | .NET only |
| "database", "migration", "query", "DbContext", "EF" | ef-core-specialist | — | .NET only |
| "write tests", "test strategy", "coverage" | test-engineer | — | .NET only |
| "build errors", "fix build", "won't compile" | build-error-resolver | — | .NET only |
| "review this code", "PR review", "code quality" | code-reviewer | — | All languages |
| "security", "authentication", "JWT", "OIDC", "authorize" | security-auditor | — | All languages |
| "performance", "benchmark", "memory", "profiling", "caching" | performance-analyst | — | All languages |
| "scaffold feature", "generate feature" | dotnet-architect | api-designer, ef-core-specialist | .NET only |
| "refactor", "clean up", "dead code" | refactor-cleaner | — | .NET only |

---

## Skill Loading Order

### Default (All Agents, All Languages)

1. **Language baseline skill** — Modern C#, TypeScript, Go, etc.
2. **Core skills** — architecture patterns, testing principles, security fundamentals
3. **Agent-specific skills** — As defined above
4. **Contextual skills** — Loaded based on codebase analysis

### Token Optimization

Agents prefer **semantic analysis tools** (MCP/LSP) over file scanning:

| Task | Use This | Instead Of |
|------|----------|-----------|
| Find symbol definition | MCP: `find_symbol` | Grep across all files |
| Find all usages | MCP: `find_references` | Grep for type name |
| List implementations | MCP: `find_implementations` | Search for `: IInterface` |
| Understand inheritance | MCP: `get_type_hierarchy` | Read multiple files |
| Understand call chains | MCP: `get_dependency_graph` | Manual file tracing |
| Review type's API | MCP: `get_public_api` | Read entire source file |
| Find unused code | MCP: `find_dead_code` | Manual inspection |
| Check circular deps | MCP: `detect_circular_dependencies` | Manual tracing |

---

## MCP/LSP Tools by Language

| Language | Primary Tool | Purpose |
|----------|-------------|---------|
| **.NET** | Roslyn Navigator | Semantic code analysis, diagnostics |
| **Node.js/TS** | TypeScript Language Server | Type inference, references |
| **Go** | Go Language Server | Symbol resolution, definitions |
| **React** | TypeScript + LSP | Same as Node.js |
| **Angular** | TypeScript + LSP | Same as Node.js |

---

## Adding New Agents

To add a new agent for a language:

1. Create `language/agents/agent-name.md`
2. Define role, skill dependencies, and response patterns
3. Update this `AGENTS.md` file with new routing entries
4. Test routing with sample project

See [EXTENSION-GUIDE.md](EXTENSION-GUIDE.md) for detailed process.
