# Supported Languages

> Registry of all supported languages, implementation status, and roadmap.

---

## Current Status

| Language | Status | Version | Agents | Skills | Commands | Templates | Last Updated |
|----------|--------|---------|--------|--------|----------|-----------|--------------|
| **.NET 10 / C# 14** | ✅ Stable | 0.1.0 | 10 | 42 | 16 | 3 | May 28, 2026 |
| **Node.js / TypeScript** | 🔜 Planned | — | — | — | — | — | — |
| **Go** | 🔜 Planned | — | — | — | — | — | — |
| **React** | 🔜 Planned | — | — | — | — | — | — |
| **Angular** | 🔜 Planned | — | — | — | — | — | — |

---

## .NET 10 / C# 14 ✅

**Status**: Stable  
**Folder**: `dotnet/`  
**Installation**: Copy `dotnet/CLAUDE.md` → `./CLAUDE.md` in your project

### What's Included

- **Agents**: 10 specialist agents (architect, API designer, EF Core, testing, security, performance, DevOps, code review, build error resolver, refactor cleaner)
- **Skills**: 42 comprehensive skills covering architecture, APIs, databases, testing, security, performance, DevOps, logging, and more
- **Commands**: 16 slash commands for project initialization, scaffolding, verification, code review, security scan, health check, etc.
- **Templates**: 3 starter templates (REST API, Modular Monolith, Worker Service)
- **MCP Tools**: Roslyn Navigator for semantic code analysis
- **Knowledge Base**: Breaking changes, antipatterns, package recommendations, ADRs

### Getting Started

```bash
# Copy the .NET kit into your project
cp polyglot-claude-kit/dotnet/CLAUDE.md ./CLAUDE.md

# Open Claude Code and try:
/dotnet-init      # Interactive project setup
/plan              # Architecture planning
/scaffold          # Feature generation
/code-review       # Multi-dimensional review
/verify            # 7-phase verification
```

### Key Features

✅ Architecture-aware (VSA, Clean Arch, DDD, Modular Monolith)  
✅ Modern C# 14 & .NET 10 patterns  
✅ OpenAPI/Minimal APIs  
✅ Entity Framework Core without repository pattern  
✅ xUnit + WebApplicationFactory + Testcontainers  
✅ CI/CD & Docker  
✅ Roslyn-powered semantic code navigation  

---

## Node.js / TypeScript 🔜

**Status**: Planned  
**Folder**: `node/` (stub - create full structure when ready)  
**ETA**: TBD

### Planned Features

- Async/await patterns & best practices
- Express.js, Fastify, other frameworks
- TypeScript configuration & patterns
- Testing: Jest, Supertest, testing-library
- ORM options: TypeORM, Prisma, Sequelize
- Dependency injection: tsyringe, InversifyJS
- npm ecosystem and package management
- CI/CD for Node projects

### Getting Started (When Available)

```bash
cp polyglot-claude-kit/node/CLAUDE.md ./CLAUDE.md
```

---

## Go 🔜

**Status**: Planned  
**Folder**: `go/` (stub - create full structure when ready)  
**ETA**: TBD

### Planned Features

- Goroutines & concurrency patterns
- Standard library HTTP handling
- Popular frameworks (Gin, Echo, Fiber)
- Testing: Go's testing package, table-driven tests
- ORM options: gorm, sqlc
- Module management & dependency resolution
- Build & deployment patterns

### Getting Started (When Available)

```bash
cp polyglot-claude-kit/go/CLAUDE.md ./CLAUDE.md
```

---

## React 🔜

**Status**: Planned  
**Folder**: `frontend/react/` (stub - create full structure when ready)  
**ETA**: TBD

### Planned Features

- React hooks & functional components
- TypeScript in React
- State management (Redux, Zustand, Context)
- Testing: Jest, React Testing Library
- Performance optimization (memo, useMemo, useCallback)
- Form handling & validation
- API integration patterns
- Component architecture & patterns

### Getting Started (When Available)

```bash
cp polyglot-claude-kit/frontend/react/CLAUDE.md ./CLAUDE.md
```

---

## Angular 🔜

**Status**: Planned  
**Folder**: `frontend/angular/` (stub - create full structure when ready)  
**ETA**: TBD

### Planned Features

- Angular components, directives, services
- TypeScript + Angular best practices
- RxJS & Observable patterns
- Testing: Jasmine, Karma, testing utilities
- Dependency injection (Angular's built-in)
- Route management & lazy loading
- State management with services or NgRx
- Performance optimization & change detection

### Getting Started (When Available)

```bash
cp polyglot-claude-kit/frontend/angular/CLAUDE.md ./CLAUDE.md
```

---

## Roadmap

### Phase 1 (Current - May 2026)
✅ .NET 10 / C# 14 — Stable & production-ready

### Phase 2 (Planned - TBD)
🔜 Node.js / TypeScript  
🔜 Go

### Phase 3 (Planned - TBD)
🔜 React  
🔜 Angular

---

## Contributing a New Language

Want to add support for a new language or tech stack? See [EXTENSION-GUIDE.md](EXTENSION-GUIDE.md) for detailed instructions.

---

## Version History

### 0.1.0 (May 28, 2026)
- Initial release with .NET 10 / C# 14 support
- Extensible architecture for multi-language support
- Core shared skills, agents, and commands
