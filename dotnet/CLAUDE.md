# dotnet-claude-kit — For .NET 10 / C# 14 Projects

> Copy this file to your .NET project root as `CLAUDE.md` to activate Claude Code expertise.

---

## Quick Start

```bash
# Copy this file to your project root
cp polyglot-claude-kit/dotnet/CLAUDE.md ./CLAUDE.md

# Open Claude Code in VS Code
# Claude will now load all .NET-specific skills and agents
```

---

## Agent Loading

The following agents are automatically loaded based on your project context:

### Specialist Agents

- **dotnet-architect** — Architecture decisions, project structure, module design, scaffolding
- **api-designer** — Minimal APIs, OpenAPI metadata, endpoint design, versioning
- **ef-core-specialist** — EF Core queries, migrations, DbContext patterns
- **test-engineer** — Test strategy, xUnit, WebApplicationFactory, Testcontainers
- **security-auditor** (shared) — Authentication, authorization, secrets
- **performance-analyst** (shared) — Profiling, caching, optimization
- **code-reviewer** (shared) — Multi-dimensional code review
- **build-error-resolver** — Autonomous build error fixing
- **refactor-cleaner** — Dead code detection and cleanup

---

## Slash Commands

Available commands in Claude Code:

### Project Setup & Planning
- `/dotnet-init` — Interactive project initialization
- `/plan` — Architecture planning with questionnaire

### Feature Development
- `/scaffold` — Complete feature generation (endpoint, handler, tests)
- `/tdd` — Test-driven development workflow

### Quality & Verification
- `/code-review` — Multi-dimensional PR review
- `/verify` — 7-phase verification (compile, test, review, security, antipatterns, coverage, deps)
- `/health-check` — Project health assessment (6 dimensions with letter grades)

### Database & Migrations
- `/migrate` — Safe EF Core migration workflow

### Maintenance & Cleanup
- `/de-sloppify` — Systematic code cleanup
- `/security-scan` — OWASP + secrets + dependency audit
- `/build-fix` — Iterative build error fixing

### Session Management
- `/checkpoint` — Save progress (git commit + handoff)
- `/wrap-up` — Session ending ritual

### Convention Learning
- `/instinct-status` — Show learned project conventions
- `/instinct-export` — Export conventions to share
- `/instinct-import` — Import conventions from another project

---

## Core Skills Loaded

### Architecture & Design
- `architecture-patterns` (from core) — VSA, Clean Architecture, DDD, Modular Monolith
- `architecture-advisor` — Framework-independent architecture questionnaire
- `project-structure` — Solution layout, Directory.Build.props, NuGet package management
- `project-setup` — Interactive initialization, health checks, migration guidance
- `vertical-slice` — VSA patterns and feature-oriented organization
- `clean-architecture` — Layered architecture: Presentation/Application/Domain/Infrastructure
- `ddd` — Domain-Driven Design: aggregates, value objects, domain events
- `scaffolding` — Feature code generation across all architecture styles
- `80-20-review` — Smart code review prioritization by blast radius

### API Development
- `minimal-api` — MapGroup, TypedResults, OpenAPI metadata, endpoint filters
- `api-versioning` — URL/header/query versioning strategies
- `error-handling` — Result pattern, ProblemDetails, validation responses
- `openapi` — OpenAPI spec generation, Scalar UI integration

### Database & Data Access
- `ef-core` — DbContext patterns, migrations, interceptors, compiled queries
- `migration-workflow` — Safe migration workflows, rollback strategies
- `configuration` — Connection strings, options pattern, environment config

### API & Service Communication
- `authentication` — JWT, OIDC, ASP.NET Identity, authorization policies
- `messaging` — Event-driven patterns, pub/sub, MassTransit, NServiceBus
- `resilience` — Retry, circuit breaker, bulkhead, timeout patterns (Polly v8)
- `httpclient-factory` — HttpClient pooling, configuration, typed clients
- `dependency-injection` — DI container setup, service registration, factory patterns

### Performance & Optimization
- `caching` (from core) — HybridCache, output caching, distributed caching patterns
- `autonomous-loops` (from core) — Bounded iteration patterns for auto-fix, auto-test

### Code Quality & Testing
- `modern-csharp` — C# 14 features: primary constructors, records, patterns, field keyword
- `testing` — xUnit v3, WebApplicationFactory, Testcontainers, Verify library, AAA pattern
- `code-review-workflow` — Structured MCP-powered review process
- `convention-learner` — Detect and enforce project-specific conventions
- `de-sloppify` — Dead code detection, unused symbols, cleanup patterns
- `verification-loop` — 7-phase verification with passing/failing criteria
- `learning-log` — Document non-obvious discoveries during development
- `instinct-system` — Pattern detection across sessions with confidence scoring

### Logging & Monitoring
- `logging` — Structured logging setup, log levels, enrichment
- `serilog` — Serilog-specific patterns, sinks, configuration
- `opentelemetry` (from core) — Distributed tracing, metrics, logs integration

### DevOps & Infrastructure
- `docker` (from core) — Multi-stage builds, health checks, non-root containers
- `ci-cd` (from core) — GitHub Actions, Azure DevOps YAML pipelines
- `aspire` — .NET Aspire orchestration, AppHost, service defaults
- `container-publish` — Registry publishing, image tagging strategies

### Specialized Patterns
- `vertical-slice` — VSA: features in Features/, complete vertical slices
- `clean-architecture` — Layered: Presentation/Application/Domain/Infrastructure
- `ddd` — Domain aggregates, value objects, domain events

### Workflow & Productivity
- `context-discipline` — Token-efficient navigation for large codebases
- `self-correction-loop` — Learn from corrections, capture rules in memory
- `wrap-up-ritual` — Session handoff documentation, progress tracking
- `workflow-mastery` — Advanced workflow orchestration patterns

---

## MCP Tools (Roslyn Navigator)

For token-efficient code analysis, this kit includes Roslyn Navigator MCP tools:

```bash
# Install Roslyn Navigator globally
dotnet tool install -g CWM.RoslynNavigator
```

### Available Tools

| Tool | Purpose | Example |
|------|---------|---------|
| `find_symbol` | Locate type/method definitions | Find where `OrderService` is defined |
| `find_references` | Find all usages of a symbol | Find all calls to `GetOrderAsync` |
| `find_implementations` | Find interface implementations | Find all `IRepository` implementations |
| `get_type_hierarchy` | Understand inheritance tree | Show what `Order` inherits from |
| `get_project_graph` | Solution dependency visualization | Understand project references |
| `get_public_api` | Review type's public surface | Check `OrderEndpoints` signatures |
| `get_diagnostics` | Compiler warnings & analyzer issues | Find all warnings in solution |
| `find_dead_code` | Identify unused types/methods | Find 50 unused symbols |
| `detect_circular_dependencies` | Find circular project dependencies | Detect circular references |
| `get_dependency_graph` | Trace method call chains | Understand call flow for debugging |
| `get_test_coverage_map` | Which types have tests | Identify untested types |
| `detect_antipatterns` | Find known anti-patterns | Detect violations in code |

---

## When to Use Each Agent

### Use `dotnet-architect` when:
- "How should I structure this project?"
- "Which architecture should I use?"
- "How do I organize features/modules?"
- "Scaffold a complete feature"

### Use `api-designer` when:
- "Create an endpoint for..."
- "How do I version my API?"
- "Add OpenAPI metadata"
- "Rate limiting strategy"

### Use `ef-core-specialist` when:
- "Write an efficient query for..."
- "Add a migration"
- "How do I handle N+1 queries?"
- "Configure DbContext"

### Use `test-engineer` when:
- "How do I test this?"
- "Write tests for..."
- "What's the coverage?"
- "Test strategy for..."

### Use `security-auditor` when:
- "How do I authenticate users?"
- "Secure this endpoint"
- "JWT best practices"
- "OWASP checklist"

### Use `performance-analyst` when:
- "This is running slow"
- "Cache this properly"
- "Profile this method"
- "Optimize memory usage"

### Use `code-reviewer` when:
- "Review this code"
- "Is this idiomatic C#?"
- "Code quality check"
- "PR review"

---

## Conventions & Standards

### Architecture
- **Default**: Vertical Slice Architecture (VSA) for new projects
- **Alternative**: Clean Architecture, DDD, or Modular Monolith if justified

### Language & Patterns
- **C# version**: C# 14 with modern patterns only
- **Constructors**: Primary constructors over traditional ones
- **DateTime**: `TimeProvider` over `DateTime.Now`
- **HTTP clients**: `IHttpClientFactory` over `new HttpClient()`
- **Repository pattern**: ❌ Not used; DbContext accessed directly

### API Design
- **Framework**: Minimal APIs (MapGroup, TypedResults)
- **Validation**: FluentValidation with filter wiring
- **Errors**: ProblemDetails with `TypedResults`
- **Versioning**: API versioning via header or URL (pick one per project)
- **OpenAPI**: Built-in .NET OpenAPI support, Scalar UI

### Database
- **ORM**: Entity Framework Core (no repository abstractions)
- **Patterns**: Compiled queries, interceptors, projections
- **Migrations**: Safe workflow with SQL review before applying

### Testing
- **Framework**: xUnit v3
- **Integration tests**: WebApplicationFactory + Testcontainers
- **Unit tests**: AAA pattern (Arrange, Act, Assert)
- **Test utilities**: Verify library for assertions

### Deployment & Infrastructure
- **Containers**: Multi-stage Docker builds, non-root users
- **Orchestration**: .NET Aspire for local dev, Kubernetes for prod
- **Health checks**: ASP.NET Core health checks endpoint

---

## Project Layout Examples

### Vertical Slice Architecture
```
src/
├── Features/
│   ├── Orders/
│   │   ├── GetOrders/
│   │   │   ├── GetOrdersEndpoint.cs
│   │   │   ├── GetOrdersHandler.cs
│   │   │   └── GetOrdersTests.cs
│   │   ├── CreateOrder/
│   │   └── OrderEntity.cs
├── Shared/
│   ├── Validators/
│   ├── Handlers/
│   └── Dto/
└── Program.cs

tests/
├── Orders.GetOrders.Tests/
├── Orders.CreateOrder.Tests/
└── Shared.Tests/
```

### Clean Architecture
```
src/
├── Presentation/
│   └── Api/
│       ├── Endpoints/
│       └── Controllers/
├── Application/
│   ├── Services/
│   ├── Dto/
│   └── Validators/
├── Domain/
│   ├── Entities/
│   └── Services/
└── Infrastructure/
    ├── Data/
    ├── Repositories/
    └── Services/

tests/
├── Application.Tests/
├── Domain.Tests/
└── Integration.Tests/
```

---

## Useful Links

- **Architecture Patterns**: See `/core/docs/architecture-patterns.md`
- **API Design Guide**: See `/core/docs/api-design-guide.md`
- **Testing Guide**: See `/core/docs/testing-guide.md`
- **Extension Guide**: See `/EXTENSION-GUIDE.md` (for adding new languages)
- **Polyglot Repo Info**: See `/LANGUAGES.md` (status of all supported languages)

---

## Troubleshooting

### Agents not loading?
- Verify `.csproj` file exists in project root or parent directories
- Restart Claude Code
- Check that this CLAUDE.md is in project root

### MCP tools not working?
```bash
# Install Roslyn Navigator
dotnet tool install -g CWM.RoslynNavigator

# Verify installation
cwm --version
```

### Commands not appearing?
- Ensure `CLAUDE.md` is in project root (not in subdirectories)
- Reload Claude Code
- Check `/verify` to diagnose issues

---

## Learning Resources

- **Recommended reading**: `core/docs/architecture-patterns.md`
- **Quick reference**: `core/docs/api-design-guide.md`
- **Testing patterns**: `core/docs/testing-guide.md`
- **Common pitfalls**: `dotnet/knowledge/common-antipatterns.md`

---

## Version & Updates

**Current version**: 0.1.0 (May 28, 2026)

Check [polyglot-claude-kit/LANGUAGES.md](../LANGUAGES.md) for latest updates and roadmap.
